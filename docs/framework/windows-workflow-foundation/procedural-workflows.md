---
title: Proceduralne przepływy pracy
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 29fc6f5ebd6bf1984f287c3d407d2564249c65f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500541"
---
# <a name="procedural-workflows"></a>Proceduralne przepływy pracy
Proceduralne przepływy pracy za pomocą metod sterowanie przepływem podobne do tych w procedurach językach. Te konstrukcje obejmują `While` i `If`. Te przepływy pracy mogą być swobodnie składane, przy użyciu innych działań sterowania przepływem, takich jak <xref:System.Activities.Statements.Flowchart> i <xref:System.Activities.Statements.Sequence>.  
  
## <a name="controlling-execution-flow"></a>Sterowanie przepływem wykonania  
 Biblioteka działań przepływu pracy ma działania dla większości metod sterowanie przepływem używanych w procedurach językach modelowania. Należą do nich następujące elementy:  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 Aby użyć działania sterowania przepływem, przeciągnij i upuść je z **działania** przybornika do działania złożonego wewnątrz okna projektanta.  
  
> [!NOTE]
>  Jeśli przy użyciu [!INCLUDE[dublin](../../../includes/dublin-md.md)] hosta przepływów pracy, w ramach farmy sieci Web AppFabric przeniesie wystąpień między różnymi serwerami AppFabric. Wymaga to, że zasoby mogą być współużytkowane przez wszystkie węzły.  Brak domyślnych działań przepływu pracy NET 4 zawierać dowolne operacje wymagające dostępu do zasobów lokalnych. Ponieważ AppFabric nie oferuje żadnych mechanizm zaznaczania przepływów pracy jako nieruchome, deweloper nie należy utworzyć niestandardowe działania, które się nie powieść, gdy przepływ pracy zostanie przeniesiony.  
  
## <a name="see-also"></a>Zobacz także
- [Przepływy pracy schematów blokowych](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
