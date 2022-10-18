```py
def call_census(zip_code, mutex, service_results):
    cens_res = c.acs5.zipcode('B01003_001E', zip_code, state_fips='*')
    with mutex:
        service_results.append(cens_res)

def get_populations_threaded(zip_codes):
    mutex = threading.Lock()
    service_results = []
    child_threads = []
    for zip_code in zip_codes:
        thread = threading.Thread(
            target=call_census,
            args=(
                zip_code,
                mutex,
                service_results,
            ),
        )
        thread.start()
        child_threads.append(thread)

    for child in child_threads:
        child.join()
    return service_results


get_populations_threaded(zip_codes)
```
