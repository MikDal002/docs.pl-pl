---
title: ". (Dostęp do elementu członkowskiego) (Jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c9d5d8f2c90273b316379d3c2803835bab3faef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="-member-access-entity-sql"></a>. (Dostęp do elementu członkowskiego) (Jednostka SQL)
Operator kropki (.) jest [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatora dostępu do elementu członkowskiego. Operator dostępu do elementu członkowskiego umożliwia uzyskanie wartość właściwości lub pola wystąpienia typu strukturalnego modelu koncepcyjnego.  
  
## <a name="syntax"></a>Składnia  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>Argumenty  
 `expression`  
 Wystąpienie typu strukturalnego modelu koncepcyjnego.  
  
 `identifier`  
 Właściwości lub pola należącego do wystąpienia obiektu.  
  
## <a name="remarks"></a>Uwagi  
 Operator kropki (.) może służyć do wyodrębniania pól z rekordu, podobnie jak Wyodrębnianie właściwości typu złożonych lub jednostki. Na przykład jeśli n Nazwa typu jest elementem członkowskim typu osoby i p jest wystąpieniem typu osoby, p.n jest wyrażenie dostępu elementu członkowskiego prawnych, zwracające wartość wpisz nazwę.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)