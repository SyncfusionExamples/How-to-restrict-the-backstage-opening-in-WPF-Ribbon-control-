# How-to-restrict-the-backstage-opening-in-WPF-Ribbon-control-
This repository contains the sample that how to restrict the backstage opening in WPF Ribbon control.

The BackStage  can be restricted from being opened by handling the BackStageOpening event of the WPF Ribbon control.
```XAML
<Syncfusion:Ribbon  Name="ribbon"   VerticalAlignment="Top">
     <Syncfusion:RibbonTab Name="tab" Caption="Home" >
          <Syncfusion:RibbonBar Header="BackStage Operations" >
              <Syncfusion:RibbonCheckBox  Content="Cancel BackStage Opening" x:Name="BackStageOpeningCheckBox"/>
              <Syncfusion:RibbonComboBox SelectedIndex="0" FlowDirection="LeftToRight" Width="110">
                   <Syncfusion:RibbonComboBoxItem>Email_Message
                   </Syncfusion:RibbonComboBoxItem>
                   <Syncfusion:RibbonComboBoxItem>Meeting</Syncfusion:RibbonComboBoxItem>
                   <Syncfusion:RibbonComboBoxItem>Appointment
                   </Syncfusion:RibbonComboBoxItem>
              </Syncfusion:RibbonComboBox>
           </Syncfusion:RibbonBar>
     </Syncfusion:RibbonTab>
</Syncfusion:Ribbon>
```
```C#
ribbon.BackStageOpening += new System.ComponentModel.CancelEventHandler(ribbon_BackStageOpening);

void ribbon_BackStageOpening(object sender, System.ComponentModel.CancelEventArgs e)
{
   if (BackStageOpeningCheckBox.IsChecked == true)
     e.Cancel = true;
}
```
Output:
The following screenshot displays how to restrict the BackStage Opening.
![WPF_Ribbon_BackStageOpening](Output_Edit_Display_FormattedHtml.png)
