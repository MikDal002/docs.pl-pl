---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c5fd2858688634ee48a67b930755fc3ceebbebf8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="bb3cd-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="bb3cd-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="bb3cd-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="bb3cd-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3cd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bb3cd-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bb3cd-105">Metody</span><span class="sxs-lookup"><span data-stu-id="bb3cd-105">Methods</span></span>  
 <span data-ttu-id="bb3cd-106">Klasa MtomMessageEncodingBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="bb3cd-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bb3cd-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="bb3cd-107">Properties</span></span>  
 <span data-ttu-id="bb3cd-108">Klasa MtomMessageEncodingBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="bb3cd-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="bb3cd-109">Kodowanie</span><span class="sxs-lookup"><span data-stu-id="bb3cd-109">Encoding</span></span>  
 <span data-ttu-id="bb3cd-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="bb3cd-110">Data type: string</span></span>  
  
 <span data-ttu-id="bb3cd-111">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="bb3cd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb3cd-112">Zestaw znaków kodowania używanego w celu emisji komunikatów w powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="bb3cd-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="bb3cd-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="bb3cd-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="bb3cd-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="bb3cd-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="bb3cd-115">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="bb3cd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb3cd-116">Liczba całkowita definiująca, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.</span><span class="sxs-lookup"><span data-stu-id="bb3cd-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="bb3cd-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="bb3cd-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="bb3cd-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="bb3cd-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="bb3cd-119">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="bb3cd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb3cd-120">Liczba całkowita definiująca, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="bb3cd-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="bb3cd-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="bb3cd-121">ReaderQuotas</span></span>  
 <span data-ttu-id="bb3cd-122">Typ danych: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="bb3cd-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="bb3cd-123">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="bb3cd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb3cd-124">Przydziały czytników.</span><span class="sxs-lookup"><span data-stu-id="bb3cd-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3cd-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bb3cd-125">Requirements</span></span>  
  
|<span data-ttu-id="bb3cd-126">MOF</span><span class="sxs-lookup"><span data-stu-id="bb3cd-126">MOF</span></span>|<span data-ttu-id="bb3cd-127">Zadeklarowany w Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bb3cd-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bb3cd-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="bb3cd-128">Namespace</span></span>|<span data-ttu-id="bb3cd-129">Zdefiniowany w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bb3cd-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb3cd-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb3cd-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>