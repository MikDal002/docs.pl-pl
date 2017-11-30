---
title: "IMetaDataImport::ResolveTypeRef — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResolveTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 390387abef5c48b4842adcfbfca126bb8292cc28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="34eb4-102">IMetaDataImport::ResolveTypeRef — Metoda</span><span class="sxs-lookup"><span data-stu-id="34eb4-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="34eb4-103">Usuwa <xref:System.Type> odwołanie reprezentowany przez określony token TypeRef.</span><span class="sxs-lookup"><span data-stu-id="34eb4-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34eb4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="34eb4-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34eb4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="34eb4-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="34eb4-106">[in] Token TypeRef metadanych do zwracania informacji typu występującego w odwołaniu do.</span><span class="sxs-lookup"><span data-stu-id="34eb4-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="34eb4-107">[in] Uzyskanie identyfikatora IID interfejsu do zwrócenia w `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="34eb4-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="34eb4-108">Zazwyczaj powinien to być IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="34eb4-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="34eb4-109">[out] Interfejs do zakresu modułu, w którym jest zdefiniowany typ, do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="34eb4-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="34eb4-110">[out] Wskaźnik do TypeDef token, który reprezentuje typ do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="34eb4-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34eb4-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="34eb4-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34eb4-112">Nie należy używać tej metody, jeśli są ładowane wielu domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="34eb4-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="34eb4-113">Metoda nie przestrzega granice domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="34eb4-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="34eb4-114">Jeśli załadowano wiele wersji zestawu zawierają ten sam typ z tego samego obszaru nazw, metoda zwraca zakres modułu pierwszego typu, który odnajdzie.</span><span class="sxs-lookup"><span data-stu-id="34eb4-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="34eb4-115">`ResolveTypeRef` Metody wyszukiwania dla definicji typu w innych modułach.</span><span class="sxs-lookup"><span data-stu-id="34eb4-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="34eb4-116">Jeśli zostanie znaleziony definicji typu, `ResolveTypeRef` zwraca interfejs do tego zakresu modułu, a także TypeDef token dla typu.</span><span class="sxs-lookup"><span data-stu-id="34eb4-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="34eb4-117">Jeśli odniesienie typu, które mają zostać rozwiązane, ma zakres rozpoznawania elementu AssemblyRef, `ResolveTypeRef` metoda szuka dopasowanie tylko w zakresach metadanych, które już zostały otwarte z wywołań albo [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)metody lub [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="34eb4-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="34eb4-118">Jest to spowodowane `ResolveTypeRef` nie można określić z tylko zakresu elementu AssemblyRef na dysku lub w pamięci podręcznej GAC zestawu przechowywania.</span><span class="sxs-lookup"><span data-stu-id="34eb4-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34eb4-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="34eb4-119">Requirements</span></span>  
 <span data-ttu-id="34eb4-120">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34eb4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34eb4-121">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34eb4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34eb4-122">**Biblioteka:** uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34eb4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34eb4-123">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34eb4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34eb4-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="34eb4-124">See Also</span></span>  
 [<span data-ttu-id="34eb4-125">IMetaDataImport — interfejs</span><span class="sxs-lookup"><span data-stu-id="34eb4-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="34eb4-126">IMetaDataImport2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="34eb4-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)