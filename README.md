# 3D Bar chart in WPF
This article explains about How to create a 3D Bar Chart in WPF. Please find below KB from more

You can create 3D bar chart in WPF by populating the items into ItemsSource of BarSeries3D series . In the following example, you will look at a grocery store. The chart displays the revenue generated from the production department.
 
 [C#]
 ```
Populated items are the sales details which denotes the products and their revenue
 
     public class Sales
    {
        public string Product { get; set; }
 
        public double Revenue { get; set; }
    }
Copy

 
     public ViewModel()
        {
            this.GrowthDetails = new ObservableCollection<Sales>();
            GrowthDetails.Add(new Sales { Product ="Pears", Revenue = 10245 });
            GrowthDetails.Add(new Sales { Product ="Apples", Revenue = 14567 });
            GrowthDetails.Add(new Sales { Product ="Tomatoes", Revenue = 32456 });
            GrowthDetails.Add(new Sales { Product ="Peas", Revenue = 31245 });
         
        }
 
        public ObservableCollection<Sales> GrowthDetails
        {

KB article - [3D Bar chart in WPF](https://www.syncfusion.com/kb/11464/how-to-create-3d-bar-chart-in-wpf)

            get; set;
        }
```

 
[XAML]
 
 ```
<Syncfusion:SfChart3D x:Name="Chart"  Header="3D Bar Chart ">
        <Syncfusion:SfChart3D.DataContext>
            <local:ViewModel/>
        </Syncfusion:SfChart3D.DataContext>
        <Syncfusion:SfChart3D.PrimaryAxis>
            <Syncfusion:CategoryAxis3D Header="Products"/>
        </Syncfusion:SfChart3D.PrimaryAxis>
 
        <Syncfusion:SfChart3D.SecondaryAxis>
            <Syncfusion:NumericalAxis3D Header="Revenue"/>
        </Syncfusion:SfChart3D.SecondaryAxis>
 
        <Syncfusion:BarSeries3D ItemsSource="{Binding GrowthDetails}" XBindingPath="Product" YBindingPath="Revenue">
            <Syncfusion:BarSeries3D.AdornmentsInfo>
                <Syncfusion:ChartAdornmentInfo3D   AdornmentsPosition="TopAndBottom" ShowLabel="true" HighlightOnSelection="True"/>
            </Syncfusion:BarSeries3D.AdornmentsInfo>
        </Syncfusion:BarSeries3D>
    </Syncfusion:SfChart3D >
    ```
KB article - [3D Bar chart](https://www.syncfusion.com/kb/11464/?utm_medium=listing&utm_source=github-examples)

