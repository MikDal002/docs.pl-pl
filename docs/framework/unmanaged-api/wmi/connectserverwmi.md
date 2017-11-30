---
title: "Funkcja ConnectServerWmi (niezarządzany wykaz interfejsów API)"
description: "Funkcja ConnectServerWmi używa modelu DCOM, aby utworzyć połączenie do przestrzeni nazw usługi WMI."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ConnectServerWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ConnectServerWmi
helpviewer_keywords: ConnectServerWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b51050bce4603ebcfe99fb38d66e54683c677293
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="7915b-103">Funkcja ConnectServerWmi</span><span class="sxs-lookup"><span data-stu-id="7915b-103">ConnectServerWmi function</span></span>
<span data-ttu-id="7915b-104">Tworzy połączenie przy użyciu modelu DCOM do przestrzeni nazw usługi WMI na określonym komputerze.</span><span class="sxs-lookup"><span data-stu-id="7915b-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7915b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="7915b-105">Syntax</span></span>  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a><span data-ttu-id="7915b-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="7915b-106">Parameters</span></span>

<span data-ttu-id="7915b-107">`strNetworkResource`[in] Wskaźnik do prawidłowej `BSTR` zawierający ścieżkę obiektu poprawną przestrzeń nazw usługi WMI.</span><span class="sxs-lookup"><span data-stu-id="7915b-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="7915b-108">Zobacz [uwagi](#remarks) sekcji, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="7915b-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="7915b-109">`strUser`[in] Wskaźnik do prawidłowej `BSTR` zawierający nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7915b-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="7915b-110">A `null` wartość wskazuje bieżący kontekst zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="7915b-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="7915b-111">Jeśli użytkownik jest z innej domeny niż bieżąca `strUser` może również zawierać nazwę domeny i użytkownika oddzielone od ukośnika odwrotnego.</span><span class="sxs-lookup"><span data-stu-id="7915b-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="7915b-112">`strUser`można również być w użytkownika nazwy głównej (UPN) sformatować, suhc jako  *userName@domainName* .</span><span class="sxs-lookup"><span data-stu-id="7915b-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="7915b-113">Zobacz [uwagi](#remarks) sekcji, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="7915b-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="7915b-114">`strPassword`[in] Wskaźnik do prawidłowej `BSTR` zawiera hasło.</span><span class="sxs-lookup"><span data-stu-id="7915b-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="7915b-115">A `null` wskazuje bieżący kontekst zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="7915b-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="7915b-116">Ciąg pusty ("") wskazuje prawidłowe hasło o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="7915b-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="7915b-117">`strLocale`[in] Wskaźnik do prawidłowej `BSTR` wskazujące poprawne ustawienia regionalne pobierania informacji.</span><span class="sxs-lookup"><span data-stu-id="7915b-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="7915b-118">Identyfikatorów ustawień regionalnych firmy Microsoft jest format ciągu "MS\_*xxx*", gdzie *xxx* jest ciągiem w postaci szesnastkowej, która wskazuje identyfikator ustawień regionalnych (LCID).</span><span class="sxs-lookup"><span data-stu-id="7915b-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="7915b-119">Jeśli określono nieprawidłowe ustawienia regionalne, metoda zwraca `WBEM_E_INVALID_PARAMETER` z wyjątkiem systemu Windows 7, gdzie domyślnych ustawień regionalnych serwera zamiast niego jest używana.</span><span class="sxs-lookup"><span data-stu-id="7915b-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="7915b-120">Jeśli "null1, bieżących ustawień regionalnych jest używany.</span><span class="sxs-lookup"><span data-stu-id="7915b-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="7915b-121">`lSecurityFlags`[in] Flagi do przekazania do `ConnectServerWmi` metody.</span><span class="sxs-lookup"><span data-stu-id="7915b-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="7915b-122">Wartość zero (0) tego parametru powoduje wywołanie `ConnectServerWmi` zwracanie tylko po nawiązaniu połączenia z serwerem.</span><span class="sxs-lookup"><span data-stu-id="7915b-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="7915b-123">Może to spowodować, że aplikacja nie odpowiada je nieskończoność Jeśli serwer jest uszkodzona.</span><span class="sxs-lookup"><span data-stu-id="7915b-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="7915b-124">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="7915b-124">The other valid values are:</span></span>

| <span data-ttu-id="7915b-125">Stała</span><span class="sxs-lookup"><span data-stu-id="7915b-125">Constant</span></span>  | <span data-ttu-id="7915b-126">Wartość</span><span class="sxs-lookup"><span data-stu-id="7915b-126">Value</span></span>  | <span data-ttu-id="7915b-127">Opis</span><span class="sxs-lookup"><span data-stu-id="7915b-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="7915b-128">0x40</span><span class="sxs-lookup"><span data-stu-id="7915b-128">0x40</span></span> | <span data-ttu-id="7915b-129">Zarezerwowany do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="7915b-129">Reserved for internal use.</span></span> <span data-ttu-id="7915b-130">Nie używać.</span><span class="sxs-lookup"><span data-stu-id="7915b-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="7915b-131">0x80</span><span class="sxs-lookup"><span data-stu-id="7915b-131">0x80</span></span> | <span data-ttu-id="7915b-132">`ConnectServerWmi`Zwraca w ciągu 2 minut lub mniej.</span><span class="sxs-lookup"><span data-stu-id="7915b-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="7915b-133">`strAuthority`[in] Nazwa domeny użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7915b-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="7915b-134">Może mieć następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="7915b-134">It can have the following values:</span></span>

| <span data-ttu-id="7915b-135">Wartość</span><span class="sxs-lookup"><span data-stu-id="7915b-135">Value</span></span> | <span data-ttu-id="7915b-136">Opis</span><span class="sxs-lookup"><span data-stu-id="7915b-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="7915b-137">Puste</span><span class="sxs-lookup"><span data-stu-id="7915b-137">blank</span></span> | <span data-ttu-id="7915b-138">Uwierzytelnianie NTLM jest używany, a używana jest Domena NTLM bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7915b-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="7915b-139">Jeśli `strUser` określa domenę (zalecana lokalizacja) nie może być określony w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="7915b-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="7915b-140">Funkcja zwraca `WBEM_E_INVALID_PARAMETER` Jeśli Określ domenę w obydwu tych parametrów.</span><span class="sxs-lookup"><span data-stu-id="7915b-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="7915b-141">Protokołu Kerberos:*nazwa główna*</span><span class="sxs-lookup"><span data-stu-id="7915b-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="7915b-142">Jest używane uwierzytelnianie Kerberos, a ten parametr zawiera nazwy głównej protokołu Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7915b-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="7915b-143">NTLMDOMAIN:*nazwy domeny*</span><span class="sxs-lookup"><span data-stu-id="7915b-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="7915b-144">Jest używane uwierzytelnianie programu NT LAN Manager, a ten parametr zawiera nazwę domeny uwierzytelnianie NTLM.</span><span class="sxs-lookup"><span data-stu-id="7915b-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="7915b-145">[in] Zazwyczaj ten parametr jest `null`.</span><span class="sxs-lookup"><span data-stu-id="7915b-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="7915b-146">W przeciwnym razie jest wskaźnik do [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) wymagany przez dostawców klasy dynamicznej co najmniej jeden obiekt.</span><span class="sxs-lookup"><span data-stu-id="7915b-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="7915b-147">[out] Po powrocie z funkcji otrzymuje wskaźnik [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) obiekt powiązany z określonego obszaru nazw.</span><span class="sxs-lookup"><span data-stu-id="7915b-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="7915b-148">Ustawiono wskaż `null` po wystąpieniu błędu.</span><span class="sxs-lookup"><span data-stu-id="7915b-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="7915b-149">[in] Poziom personifikacji.</span><span class="sxs-lookup"><span data-stu-id="7915b-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="7915b-150">[in] Poziom autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="7915b-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="7915b-151">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7915b-151">Return value</span></span>

<span data-ttu-id="7915b-152">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="7915b-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7915b-153">Stała</span><span class="sxs-lookup"><span data-stu-id="7915b-153">Constant</span></span>  |<span data-ttu-id="7915b-154">Wartość</span><span class="sxs-lookup"><span data-stu-id="7915b-154">Value</span></span>  |<span data-ttu-id="7915b-155">Opis</span><span class="sxs-lookup"><span data-stu-id="7915b-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="7915b-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7915b-156">0x80041001</span></span> | <span data-ttu-id="7915b-157">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="7915b-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7915b-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7915b-158">0x80041008</span></span> | <span data-ttu-id="7915b-159">Parametr jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="7915b-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7915b-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7915b-160">0x80041006</span></span> | <span data-ttu-id="7915b-161">Za mało pamięci jest dostępna do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="7915b-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7915b-162">0</span><span class="sxs-lookup"><span data-stu-id="7915b-162">0</span></span> | <span data-ttu-id="7915b-163">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="7915b-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7915b-164">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7915b-164">Remarks</span></span>

<span data-ttu-id="7915b-165">Ta funkcja jest zawijana wywołanie [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="7915b-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="7915b-166">Lokalnego dostępu do domyślnej przestrzeni nazw `strNetworkResource` może być ścieżką prostego obiektu: "root\default" lub "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="7915b-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="7915b-167">Aby uzyskać dostęp do domyślnej przestrzeni nazw na komputerze zdalnym przy użyciu modelu COM lub zgodny z programem Microsoft sieci, dołączyć nazwę komputera: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="7915b-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="7915b-168">Nazwa komputera może również zawierać nazwę DNS lub adres IP.</span><span class="sxs-lookup"><span data-stu-id="7915b-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="7915b-169">`ConnectServerWmi` Funkcja umożliwia też łączność z komputerami z systemem IPv6 przy użyciu adresu IPv6.</span><span class="sxs-lookup"><span data-stu-id="7915b-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="7915b-170">`strUser`nie może być pustym ciągiem.</span><span class="sxs-lookup"><span data-stu-id="7915b-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="7915b-171">Jeśli zostanie określona domena, w `strAuthority`, go nie może również być uwzględniony w `strUser`, lub funkcja zwraca `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="7915b-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="7915b-172">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7915b-172">Requirements</span></span>  
 <span data-ttu-id="7915b-173">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7915b-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7915b-174">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7915b-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7915b-175">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7915b-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7915b-176">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7915b-176">See also</span></span>  
[<span data-ttu-id="7915b-177">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="7915b-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)