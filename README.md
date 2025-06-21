# Healthcare Patient Waiting List Dashboard

A comprehensive Power BI dashboard for tracking and analyzing patient waiting lists across healthcare facilities, providing insights into inpatient and outpatient trends, specialty-level analysis, and age profile breakdowns.

## 📊 Dashboard Preview

### Summary Page

![Dashboard Summary](Dashboard_summary.png)

### Detailed Analysis Page

![Dashboard Details](Dashboard_Details.png)

## 🎯 Project Objectives

- **Track Current Status**: Monitor real-time patient waiting list metrics
- **Historical Analysis**: Analyze monthly trends in inpatient and outpatient categories
- **Specialty Insights**: Detailed specialty-level and age profile analysis
- **Data-Driven Decisions**: Enable healthcare administrators to make informed decisions

## 📈 Key Features

### 🔍 **Dynamic Analysis**

- Toggle between **Average** and **Median** calculations using interactive button slicers
- Real-time filtering by date range, case type, and medical specialty
- Comprehensive drill-down capabilities from summary to detailed views

### 📊 **Visual Components**

- **KPI Cards**: Latest month and previous year waiting list metrics
- **Trend Analysis**: Line charts showing historical waiting list patterns
- **Distribution Charts**: Doughnut charts for case type breakdown
- **Ranking Visuals**: Top 5 specialties with highest waiting lists
- **Matrix View**: Detailed tabular analysis with multiple dimensions

### 🎨 **Interactive Elements**

- **Custom Tooltips**: Hover over charts for additional specialty-specific insights
- **Navigation Buttons**: Seamless movement between summary and detailed pages
- **Smart Filtering**: Cross-visual filtering for comprehensive analysis
- **Responsive Design**: Optimized layout with gridlines and snap-to-grid alignment

## 📅 Data Scope

- **Time Period**: 2018 - 2021
- **Categories**: Inpatient, Outpatient, Day Case
- **Granularity**: Monthly trending with specialty and age profile breakdowns

## 🛠️ Technical Implementation

### **Data Architecture**

- **Data Sources**: Centralized folder structure for automated refresh
- **ETL Process**: Power Query transformations including column standardization and data cleaning
- **Data Model**: Star schema with specialty mapping for categorization
- **Refresh Strategy**: Automated monthly refresh process

### **Advanced DAX Measures**

```dax
Latest Month Wait List = CALCULATE(SUM(All_Data[Total]),All_Data[Archive_Date] = MAX(All_Data[Archive_Date])) + 0

PY Latest Month Wait List = CALCULATE(SUM(All_Data[Total]),All_Data[Archive_Date]= EDATE(MAX(All_Data[Archive_Date]),-12)) + 0

Avg/Med Wait List = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average",[Average Wait List],"Median",[Median Wait List])

Dynamic Title = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average","Key Indicators - Patient Wait List (Average)","Median","Key Indicators - Patient Wait List (Median)")
```

### **Data Quality Features**

- Automated data validation and anomaly detection
- Missing value handling and data cleansing
- Trailing space removal and text standardization
- Conditional formatting for data availability

## 🔧 Setup Instructions

### **Prerequisites**

- Power BI Desktop (Latest Version)
- Access to healthcare waiting list data files
- Basic understanding of Power BI interface

### **Installation Steps**

1. **Data Setup**: Extract data files to a centralized folder structure
2. **Import Process**: Use Power BI folder connector to import inpatient and outpatient data
3. **Data Transformation**: Apply Power Query transformations for data standardization
4. **Model Configuration**: Establish relationships between main data and specialty mapping tables
5. **Measure Creation**: Implement DAX measures for calculations and dynamic titles
6. **Visualization Build**: Construct charts and visuals according to the blueprint design
7. **Interactivity Setup**: Configure slicers, navigation, and tooltip pages

## 📋 Key Metrics Tracked

| Metric                       | Description                                        | Calculation Method             |
| ---------------------------- | -------------------------------------------------- | ------------------------------ |
| **Current Total Wait List**  | Current month's total waiting patients             | SUM of latest month data       |
| **Previous Year Comparison** | Year-over-year waiting list comparison             | 12-month historical comparison |
| **Average Wait List**        | Mean waiting list across time periods              | AVERAGE function               |
| **Median Wait List**         | Median waiting list for outlier-resistant analysis | MEDIAN function                |
| **Specialty Rankings**       | Top performing/challenged specialties              | Ranked totals by specialty     |

## 🎨 Design Principles

- **Professional Healthcare Theme**: Clean, medical-appropriate color palette
- **Intuitive Navigation**: User-friendly interface with clear visual hierarchy
- **Mobile Responsive**: Optimized for various screen sizes and devices
- **Accessibility**: High contrast ratios and readable fonts
- **Performance Optimized**: Efficient DAX measures and optimized data model

## 📊 Business Value

### **For Healthcare Administrators**

- Real-time visibility into patient waiting lists
- Identify bottlenecks and resource allocation opportunities
- Track performance against historical benchmarks
- Specialty-level insights for targeted improvements

### **For Operations Teams**

- Monthly trend analysis for capacity planning
- Age profile insights for demographic planning
- Case type distribution for resource optimization
- Data-driven decision making capabilities

## 🔄 Maintenance & Updates

- **Monthly Data Refresh**: Automated process for current data integration
- **Quality Assurance**: Built-in data validation and error handling
- **Performance Monitoring**: Regular optimization of DAX measures and data model
- **User Feedback Integration**: Continuous improvement based on stakeholder input

## 📈 Future Enhancements

- **Predictive Analytics**: Forecasting future waiting list trends
- **Real-time Integration**: Live data connectivity for up-to-the-minute insights
- **Advanced Segmentation**: Additional demographic and clinical categorization
- **Mobile App Integration**: Native mobile dashboard experience
- **Automated Alerts**: Threshold-based notifications for critical metrics

## 🏥 Use Cases

- **Hospital Management**: Strategic planning and resource allocation
- **Department Heads**: Specialty-specific performance monitoring
- **Operations Planning**: Capacity management and scheduling optimization
- **Quality Improvement**: Identifying areas for process enhancement
- **Regulatory Reporting**: Compliance and performance reporting

---

_This dashboard represents a comprehensive solution for healthcare waiting list management, combining robust data analysis with intuitive visualization to drive operational excellence in patient care delivery._
