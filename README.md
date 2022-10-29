# Blazor Chart Axis Label Customization
This example show how to customize the blazor chart axis label. 

```cshtml

@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnAxisLabelRender="AxisLabelEvent"></ChartEvents>
	
    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
	
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month { get; set; }
        public double SalesValue { get; set; }
    }
	
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void AxisLabelEvent(AxisLabelRenderEventArgs args)
    {
       if (args.Axis.Name == "PrimaryXAxis")
        {
            args.LabelStyle.Color = "Red";
             if (args.Value == 4)
             args.Text = "chart"; 

        } else if (args.Axis.Name == "PrimaryYAxis")
        {
            args.LabelStyle.Color = "Blue";

        } 
    }
}

```

## Prerequisites

* Visual Studio 2022

## How to run the project

* Checkout this repository in your local disk.
* Open the solution file using the Visual Studio 2022.
* Restore the NuGet packages by rebuilding the solution.
* Run the project.