---
title: "Porady: Użyj EdmGen.exe, aby wygenerować kod warstwy obiektu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4abb20ca2ff26fa4e2105bae87274028592aa510
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="31da7-102">Porady: Użyj EdmGen.exe, aby wygenerować kod warstwy obiektu</span><span class="sxs-lookup"><span data-stu-id="31da7-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="31da7-103">W tym temacie przedstawiono sposób użycia [Generator EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) narzędzie do generowania kodu warstwy obiektu oparte na pliku CSDL.</span><span class="sxs-lookup"><span data-stu-id="31da7-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="31da7-104">Aby wygenerować kod warstwy obiektu dla modelu służbowych przy użyciu EdmGen.exe projektu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31da7-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="31da7-105">Utwórz bazę danych służbowych.</span><span class="sxs-lookup"><span data-stu-id="31da7-105">Create the School database.</span></span> <span data-ttu-id="31da7-106">Aby uzyskać więcej informacji, zobacz [tworzenie przykładowej bazy danych służbowych](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="31da7-106">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="31da7-107">Generowanie modelu służbowe lub pobrać plik School.csdl.</span><span class="sxs-lookup"><span data-stu-id="31da7-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="31da7-108">Aby uzyskać więcej informacji, zobacz [porady: EdmGen.exe używany do generowania modelu i mapowania plików](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="31da7-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="31da7-109">W wierszu polecenia Uruchom następujące polecenie bez podziałów wierszy:</span><span class="sxs-lookup"><span data-stu-id="31da7-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="31da7-110">Aby wygenerować kod warstwy obiektu modelu służbowe dla projektu C# za pomocą EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="31da7-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="31da7-111">Utwórz bazę danych służbowych.</span><span class="sxs-lookup"><span data-stu-id="31da7-111">Create the School database.</span></span> <span data-ttu-id="31da7-112">Aby uzyskać więcej informacji, zobacz [tworzenie przykładowej bazy danych służbowych](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="31da7-112">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="31da7-113">Generowanie modelu służbowe lub pobrać plik School.csdl.</span><span class="sxs-lookup"><span data-stu-id="31da7-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="31da7-114">Aby uzyskać więcej informacji, zobacz [porady: EdmGen.exe używany do generowania modelu i mapowania plików](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="31da7-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="31da7-115">W wierszu polecenia Uruchom następujące polecenie bez podziałów wierszy:</span><span class="sxs-lookup"><span data-stu-id="31da7-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31da7-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="31da7-116">See Also</span></span>  
 [<span data-ttu-id="31da7-117">Mapowanie i modelowania</span><span class="sxs-lookup"><span data-stu-id="31da7-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="31da7-118">Porady: ręczne konfigurowanie projektu programu Entity Framework</span><span class="sxs-lookup"><span data-stu-id="31da7-118">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="31da7-119">ADO.NET Entity Data Model Tools</span><span class="sxs-lookup"><span data-stu-id="31da7-119">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="31da7-120">Porady: wstępnego wygenerowania widoków, aby poprawić wydajność zapytań</span><span class="sxs-lookup"><span data-stu-id="31da7-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="31da7-121">Porady: Generowanie modelu i mapowania plików za pomocą EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="31da7-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)