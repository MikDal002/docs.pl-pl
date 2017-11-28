---
title: "Niestandardowe projektantów złożonego - Prezenterze element przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3fa40a7a864ae65d15d787f5dec58a8da7b8e9a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Niestandardowe projektantów złożonego - Prezenterze element przepływu pracy
<xref:System.Activities.Presentation.WorkflowItemPresenter> Jest typem klucza w WF projektanta programowania modelu, który umożliwia tworzenie "strefy docelowej" rozmieszczenia dowolnego działania. W tym przykładzie przedstawiono sposób tworzenia Projektant działań tego powierzchni takiej "upuszczania strefy."  
  
 W tym przykładzie przedstawiono:  
  
## <a name="demonstrates"></a>Demonstracje  
  
-   Tworzenie Projektant działań niestandardowych z <xref:System.Activities.Presentation.WorkflowItemPresenter>.  
  
-   Rejestrowanie niestandardowe projektanta przy użyciu magazynu metadanych.  
  
-   Programowanie przybornika rehosted deklaratywnie i imperatively.  
  
## <a name="sample-details"></a>Szczegóły próbki  
 Dla tego przykładu kod:  
  
-   Projektant działań niestandardowych zaprojektowano pod kątem `SimpleNativeActivity` klasy.  
  
-   Tworzenie Projektant działań niestandardowych z <xref:System.Activities.Presentation.WorkflowItemPresenter>.  
  
```xaml  
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
    <sap:ActivityDesigner.Resources>  
        <DataTemplate x:Key="Collapsed">  
            <StackPanel>  
                <TextBlock>This is the collapsed view</TextBlock>  
            </StackPanel>  
        </DataTemplate>  
        <DataTemplate x:Key="Expanded">  
            <StackPanel>  
                <TextBlock>Custom Text</TextBlock>  
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                        HintText="Please drop an activity here" />  
            </StackPanel>  
        </DataTemplate>  
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
            <Style.Triggers>  
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                </DataTrigger>  
            </Style.Triggers>  
        </Style>  
    </sap:ActivityDesigner.Resources>  
    <Grid>  
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
    </Grid>  
</sap:ActivityDesigner>  
```  
  
 Zwróć uwagę na użycie powiązanie danych WPF powiązać `ModelItem.Body`. `ModelItem`jest właściwością na <xref:System.Activities.Presentation.ActivityDesigner> odwołujący się do obiektu źródłowego projektanta jest używany, w tym przypadku **SimpleNativeActivity**.  
  
#### <a name="to-setup-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić próbki  
  
1.  Otwórz rozwiązanie w [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Naciśnij klawisz F5, aby skompilować i uruchomić aplikację.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [Tworzenie aplikacji za pomocą projektanta przepływów pracy](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)