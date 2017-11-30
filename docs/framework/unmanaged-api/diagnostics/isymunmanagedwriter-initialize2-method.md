---
title: "ISymUnmanagedWriter::Initialize2 — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e76543c35a717b95ae37985648986abaf16bf85d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="02620-102">ISymUnmanagedWriter::Initialize2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="02620-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="02620-103">Ustawienie interfejsu nadajnika metadanych, z którą ten moduł zapisujący zostanie skojarzony, a nazwa pliku wyjściowego, na którym zostanie zapisany symbole debugowania.</span><span class="sxs-lookup"><span data-stu-id="02620-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="02620-104">Ta metoda umożliwia również ustawić ostatecznej lokalizacji pliku programu (PDB) bazy danych.</span><span class="sxs-lookup"><span data-stu-id="02620-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02620-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="02620-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02620-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="02620-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="02620-107">[in] Wskaźnik do interfejsu nadajnika metadanych.</span><span class="sxs-lookup"><span data-stu-id="02620-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="02620-108">[in] Wskaźnik do `WCHAR` zawierający nazwę pliku, do którego są zapisywane symbole debugowania.</span><span class="sxs-lookup"><span data-stu-id="02620-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="02620-109">Jeśli nazwa pliku jest określona dla składnika zapisywania, która nie korzysta z nazw plików, ten parametr jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="02620-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="02620-110">[in] Jeśli zostanie określona, moduł zapisujący symbol emituje symbole w danym <xref:System.Runtime.InteropServices.ComTypes.IStream> , a nie do pliku określonego w `filename` parametru.</span><span class="sxs-lookup"><span data-stu-id="02620-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="02620-111">`pIStream` Parametr jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="02620-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="02620-112">[in] `true` Jeśli jest to ponownej pełnej kompilacji; `false` Jeśli jest to kompilacji przyrostowej.</span><span class="sxs-lookup"><span data-stu-id="02620-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="02620-113">[in] Wskaźnik do `WCHAR` oznacza to ciąg ścieżki do ostatecznego lokalizację pliku PDB.</span><span class="sxs-lookup"><span data-stu-id="02620-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02620-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="02620-114">Return Value</span></span>  
 <span data-ttu-id="02620-115">Wartość S_OK, jeśli metoda zakończy się pomyślnie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="02620-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02620-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="02620-116">Requirements</span></span>  
 <span data-ttu-id="02620-117">**Nagłówek:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="02620-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02620-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="02620-118">See Also</span></span>  
 [<span data-ttu-id="02620-119">ISymUnmanagedWriter — interfejs</span><span class="sxs-lookup"><span data-stu-id="02620-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="02620-120">Initialize — metoda</span><span class="sxs-lookup"><span data-stu-id="02620-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)