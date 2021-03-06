---
title: <include> - C# Przewodnik programowania
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 1e933647487f966e9f8448cf60a2bdecdd29cdff
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286272"
---
# <a name="include-c-programming-guide"></a>\<obejmują > (C# Programming Guide)
## <a name="syntax"></a>Składnia  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a>Parametry  
 `filename`  
 Nazwa pliku XML zawierającego dokumentację. Nazwa pliku może być kwalifikowana ze ścieżką względną do pliku kodu źródłowego. Ujmij `filename` w znaki pojedynczego cudzysłowu ("").  
  
 `tagpath`  
 Ścieżka znaczniki `filename` prowadzi to do tagu `name`. Zamknij ścieżkę w znaki pojedynczego cudzysłowu ("").  
  
 `name`  
 Określenie nazwy w tagu, który poprzedza komentarzy; `name` będzie miał `id`.  
  
 `id`  
 Identyfikator tagu, który poprzedza komentarze. Umieść identyfikator w podwójnym cudzysłowie ("").  
  
## <a name="remarks"></a>Uwagi  
 \<Obejmują > tag pozwala odwoływać się do komentarzy w innym pliku, które opisują typy i elementy członkowskie w kodzie źródłowym. Jest to alternatywa do wprowadzania komentarzy dokumentacji bezpośrednio w pliku kodu źródłowego. Poprzez umieszczenie dokumentacji w oddzielnym pliku, można zastosować kontroli źródła z dokumentacją oddzielnie z kodu źródłowego. Jedna osoba może mieć wyewidencjonować pliku źródła kodu, a ktoś inny może mieć plik dokumentacji wyewidencjonowany.  
  
 \<Obejmują > tag używa składni XML XPath. Zajrzyj do dokumentacji wyrażenie XPath sposoby dostosowywania swoje \<obejmują > Użyj.  
  
## <a name="example"></a>Przykład  
 To jest przykład wieloplikowego. Pierwszy plik, który używa \<obejmują >, znajduje się poniżej:  
  
 [!code-csharp[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 Drugi plik, xml_include_tag.doc, zawiera następujące komentarzy dokumentacji:  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a>Dane wyjściowe programu  
 Następujące dane wyjściowe są generowane podczas kompilowania z klas testowych i Test2 za pomocą następującego polecenia: `/doc:DocFileName.xml.` W programie Visual Studio określasz XML dokumentacji opcja komentarze w okienku kompilacji w Projektancie projektu. Gdy C# widzi kompilator \<obejmują > tag, przeszukiwane są przeznaczone do komentarzy dokumentacji w xml_include_tag.doc zamiast bieżącego pliku źródłowego. Kompilator generuje następnie DocFileName.xml i to jest plik, który jest używany przez narzędzia, dokumentację, takich jak [DocFX](https://dotnet.github.io/docfx/) i [Sandcastle](https://github.com/EWSoftware/SHFB) do produkcji dokumentację.  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a>Zobacz także

- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [Zalecane tagi przeznaczone do komentarzy dokumentacji](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
