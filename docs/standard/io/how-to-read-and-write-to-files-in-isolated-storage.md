---
title: 'Instrukcje: Odczyt i zapis w plikach w wydzielonej pamięci masowej'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59a89aa354941b7ff22a125a980c2d9c75ac37ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491526"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Instrukcje: Odczyt i zapis w plikach w wydzielonej pamięci masowej
Odczyt i zapis do pliku w izolowanym magazynie, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> obiektu z czytnik strumienia (<xref:System.IO.StreamReader> obiekt) lub zapisywania do strumienia (<xref:System.IO.StreamWriter> obiektu).  
  
## <a name="example"></a>Przykład  
 Poniższy przykładowy kod uzyskuje izolowanym magazynie i sprawdza, czy plik o nazwie TestStore.txt istnieje w magazynie. Jeśli nie istnieje, tworzy plik i zapisuje "Hello wydzielonej pamięci masowej" do pliku. Jeśli istnieje już TestStore.txt, przykładowy kod odczytuje z pliku.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [We/Wy plików i strumieni](../../../docs/standard/io/index.md)
- [Wydzielona pamięć masowa](../../../docs/standard/io/isolated-storage.md)
