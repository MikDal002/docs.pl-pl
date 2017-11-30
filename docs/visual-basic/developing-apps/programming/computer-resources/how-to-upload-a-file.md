---
title: "Porady: ładowanie pliku w Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a0fab9b812ddff1f56e9fa203bd297fd70bc47d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="d3bad-102">Porady: ładowanie pliku w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3bad-102">How to: Upload a File in Visual Basic</span></span>
<span data-ttu-id="d3bad-103"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> Metoda może służyć do przekazania pliku i zapisz go w lokalizacji zdalnej.</span><span class="sxs-lookup"><span data-stu-id="d3bad-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="d3bad-104">Jeśli `ShowUI` ustawiono parametr `True`, wyświetlane jest okno dialogowe, będzie wyświetlany postęp przekazywania, który umożliwia użytkownikom anulować operację.</span><span class="sxs-lookup"><span data-stu-id="d3bad-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="d3bad-105">Aby przekazać plik</span><span class="sxs-lookup"><span data-stu-id="d3bad-105">To upload a file</span></span>  
  
-   <span data-ttu-id="d3bad-106">Użyj `UploadFile` metody, aby przekazać plik, określając lokalizację pliku źródłowego i docelowego lokalizacji katalogu jako ciągu lub identyfikator URI (Uniform Resource Identifier). W tym przykładzie powoduje przekazanie pliku `Order.txt` do `http://www.cohowinery.com/uploads.aspx`.</span><span class="sxs-lookup"><span data-stu-id="d3bad-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="d3bad-107">Aby przekazać plik i wyświetlić postęp operacji</span><span class="sxs-lookup"><span data-stu-id="d3bad-107">To upload a file and show the progress of the operation</span></span>  
  
-   <span data-ttu-id="d3bad-108">Użyj `UploadFile` metody, aby przekazać plik, określając lokalizację pliku źródłowego i docelowego lokalizacji katalogu jako ciągu lub identyfikator URI.</span><span class="sxs-lookup"><span data-stu-id="d3bad-108">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="d3bad-109">W tym przykładzie powoduje przekazanie pliku `Order.txt` do `http://www.cohowinery.com/uploads.aspx` bez podawania nazwy użytkownika ani hasła, będzie wyświetlany postęp przekazywania i ma limit czasu 500 milisekund.</span><span class="sxs-lookup"><span data-stu-id="d3bad-109">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="d3bad-110">Aby przekazać plik, podając nazwę użytkownika i hasło</span><span class="sxs-lookup"><span data-stu-id="d3bad-110">To upload a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="d3bad-111">Użyj `UploadFile` metody, aby przekazać plik, określić lokalizację pliku źródłowego i docelowego lokalizacji katalogu jako ciągu lub identyfikator URI, a następnie określając nazwę użytkownika i hasło.</span><span class="sxs-lookup"><span data-stu-id="d3bad-111">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="d3bad-112">W tym przykładzie powoduje przekazanie pliku `Order.txt` do `http://www.cohowinery.com/uploads.aspx`, podanie nazwy użytkownika `anonymous` i pustego hasła.</span><span class="sxs-lookup"><span data-stu-id="d3bad-112">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d3bad-113">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="d3bad-113">Robust Programming</span></span>  
 <span data-ttu-id="d3bad-114">Poniższe warunki mogą zgłosić wyjątek:</span><span class="sxs-lookup"><span data-stu-id="d3bad-114">The following conditions may throw an exception:</span></span>  
  
-   <span data-ttu-id="d3bad-115">Ścieżka pliku lokalnego jest nieprawidłowa (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="d3bad-115">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="d3bad-116">Uwierzytelnianie nie powiodło się (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="d3bad-116">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="d3bad-117">Upłynął limit czasu połączenia (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="d3bad-117">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bad-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3bad-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>  
 [<span data-ttu-id="d3bad-119">Porady: pobieranie pliku</span><span class="sxs-lookup"><span data-stu-id="d3bad-119">How to: Download a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)  
 [<span data-ttu-id="d3bad-120">Porady: analizowanie ścieżek pliku</span><span class="sxs-lookup"><span data-stu-id="d3bad-120">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)