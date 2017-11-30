---
title: "Funkcja GetPropertyHandle (niezarządzany wykaz interfejsów API)"
description: "Funkcja GetPropertyHandle zwraca uchwyt unikatowy tej właściwości tożsamości."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="38e9a-103">Funkcja GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="38e9a-103">GetPropertyHandle function</span></span>
<span data-ttu-id="38e9a-104">Zwraca unikatowy dojścia identyfikujący właściwości.</span><span class="sxs-lookup"><span data-stu-id="38e9a-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="38e9a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="38e9a-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="38e9a-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="38e9a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="38e9a-107">[in] Ten parametr nie jest używana.</span><span class="sxs-lookup"><span data-stu-id="38e9a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="38e9a-108">[in] Wskaźnik do [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="38e9a-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="38e9a-109">[in] Zerem ciąg kodowany w formacie UTF16 characaters, który zawiera nazwę właściwości.</span><span class="sxs-lookup"><span data-stu-id="38e9a-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="38e9a-110">[out] Wskaźnik do [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) element członkowski wyliczenia, który reprezentuje typ CIM właściwości.</span><span class="sxs-lookup"><span data-stu-id="38e9a-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="38e9a-111">[out] Wskaźnik do liczba całkowita, która zawiera dojście właściwości.</span><span class="sxs-lookup"><span data-stu-id="38e9a-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="38e9a-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="38e9a-112">Return value</span></span>

<span data-ttu-id="38e9a-113">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="38e9a-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="38e9a-114">Stała</span><span class="sxs-lookup"><span data-stu-id="38e9a-114">Constant</span></span>  |<span data-ttu-id="38e9a-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="38e9a-115">Value</span></span>  |<span data-ttu-id="38e9a-116">Opis</span><span class="sxs-lookup"><span data-stu-id="38e9a-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="38e9a-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="38e9a-117">0x80041002</span></span> | <span data-ttu-id="38e9a-118">Określona nazwa właściwości nie został znaleziony.</span><span class="sxs-lookup"><span data-stu-id="38e9a-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="38e9a-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="38e9a-119">0x80041008</span></span> | <span data-ttu-id="38e9a-120">Parametr jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="38e9a-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="38e9a-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="38e9a-121">0x8004100c</span></span> | <span data-ttu-id="38e9a-122">Żądana właściwość jest typu są `CIM_OBJECT` lub `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="38e9a-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="38e9a-123">0</span><span class="sxs-lookup"><span data-stu-id="38e9a-123">0</span></span> | <span data-ttu-id="38e9a-124">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="38e9a-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="38e9a-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="38e9a-125">Remarks</span></span>

<span data-ttu-id="38e9a-126">Ta funkcja jest zawijana wywołanie [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="38e9a-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="38e9a-127">Przy użyciu tego uchwytu do identyfikowania właściwości, korzystając z [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) metod do odczytu lub zapisu wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="38e9a-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="38e9a-128">Uchwyty można pobrać właściwości wszystkich typów danych innych niż `CIM_OBJECT` i `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="38e9a-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="38e9a-129">Zwracane pracy uchwytów we wszystkich wystąpieniach klasy.</span><span class="sxs-lookup"><span data-stu-id="38e9a-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="38e9a-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="38e9a-130">Requirements</span></span>  
<span data-ttu-id="38e9a-131">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e9a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e9a-132">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="38e9a-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="38e9a-133">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="38e9a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e9a-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="38e9a-134">See also</span></span>  
[<span data-ttu-id="38e9a-135">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="38e9a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)