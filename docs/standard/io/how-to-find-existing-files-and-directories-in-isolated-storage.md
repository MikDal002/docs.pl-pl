---
title: "Porady: wyszukiwanie istniejących plików i katalogów w izolowanym magazynie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Porady: wyszukiwanie istniejących plików i katalogów w izolowanym magazynie
Aby wyszukać katalog w magazynie izolowanym, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> metody. Ta metoda przyjmuje ciąg, który reprezentuje wzorzec wyszukiwania. Można użyć zarówno jednoznakowym (?) i wielu znaków (*) znaki symboli wieloznacznych we wzorcu wyszukiwania, ale symboli wieloznacznych musi występować w końcowa część nazwy. Na przykład `directory1/*ect*` jest prawidłowy ciąg wyszukiwania, ale `*ect*/directory2` nie jest.  
  
 Aby wyszukać plik, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> metody. Ograniczenie dla symbole wieloznaczne w ciągach wyszukiwania, których dotyczy <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> dotyczą również <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Żadna z tych metod jest rekursywny; <xref:System.IO.IsolatedStorage.IsolatedStorageFile> klasa nie dostarcza żadnych metod do wyświetlania listy wszystkich katalogów lub plików w magazynie. Jednak rekursywny metod przedstawiono w poniższym przykładzie kodu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykładowy kod ilustruje sposób tworzenia plików i katalogów w izolowanym magazynie. Najpierw należy pobrać i umieszczane w sklepu, która jest odizolowana dla użytkownika, domena i zestawu `isoStore` zmiennej. <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> Metoda jest używana do konfigurowania kilku różnych katalogach i <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> Konstruktor tworzy niektóre pliki w tych katalogach. Kod następnie pętli wyniki `GetAllDirectories` metody. Ta metoda używa <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> można znaleźć nazwy katalogów w bieżącym katalogu. Te nazwy są przechowywane w tablicy, a następnie `GetAllDirectories` wywołuje, przekazując każdego katalogu znaleziono. W związku z tym zwracane są wszystkie nazwy katalogów w tablicy. Następnie kod wywołuje `GetAllFiles` metody. Ta metoda wywołuje `GetAllDirectories` Aby dowiedzieć się, nazwy wszystkich katalogów, a następnie sprawdza każdy katalog dla plików przy użyciu <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> metody. Wynik jest zwracany w tablicy do wyświetlenia.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Izolowany Magazyn](../../../docs/standard/io/isolated-storage.md)