1.Below is our XAML. It will contain a button we will click to fire the async and non async method and also a text box to show how async
works.
```xml
    <Grid>
        <Button Click="ButtonBase_OnClick" Content="Button" HorizontalAlignment="Center" VerticalAlignment="Center"/>      
        <TextBox VerticalAlignment="Bottom" HorizontalAlignment="Left" Name="Block" Width="19" Height="20"></TextBox>
    </Grid>
```
2. Below is our C#
```cs
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }
        
        //here is our button click method it needs to go and grab data and download it to a file, once that is done, it needs
        //to turn the back of our text area red.
        private void ButtonBase_OnClick(object sender, RoutedEventArgs e)
        {
            //below is the non async method, the entire method will need to finsih running before the text are turns red
            //as the next line below imstructs it.
            DownloadHtml("http://msdn.microsoft.com"); 
            Block.Background = Brushes.Red;
        }

        public void DownloadHtml(string url)
        {
            // all of this code will need to finish running, before line 25 will ever begin to run.
            var webClient = new WebClient();
            var html = webClient.DownloadString(url);

            using (var stream = new StreamWriter(@"C:\Users\16512\Anaconda3\result.html"))
            {
                stream.Write(html);
            }
        }

        public async Task DownloadHtmlAsync(string url)
        {
            var webClient = new WebClient();
            //now in the async version here, the line below will begin to run, and instantly, the code will go back up
            //to line 25 to run the code, so that our ui does not freeze up. 
            var html = await webClient.DownloadStringTaskAsync(url);
            
            //AFTER THE LINE ABOVE FINISHES RUNNING, THEN AND ONLY THEN WILL THE CODE BEGIN TO EXECUTE, AND THIS IS ALL
            //AFTER LINE 25 HAS BEGAN/FINISHED EXECUTING
            using (var stream = new StreamWriter(@"C:\Users\16512\Anaconda3\result.html"))
            {
                stream.Write(html);
            }
        }
    }
```
