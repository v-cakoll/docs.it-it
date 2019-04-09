---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: d4293b8e027f7f0f7eabac7ad9c8a9852ddd3a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178477"
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Crea un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore MULTISET devono essere di un tipo `T`compatibile. Non sono consentiti costruttori multiset vuoti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi elenco valido di valori.  
  
## <a name="return-value"></a>Valore restituito  
 Una raccolta di tipo MULTISET\<T >.  
  
## <a name="remarks"></a>Note  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce tre tipi di costruttori: costruttori di riga, costruttori di oggetti e costruttori multiset (o raccolta). Per altre informazioni, vedere [tipi di costruzione](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 Il costruttore multiset crea un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore devono essere di un tipo compatibile.  
  
 L'espressione seguente consente ad esempio di creare un multiset di valori interi.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  Valori letterali di multiset annidati sono supportati solo quando un multiset di wrapping contiene un solo elemento multiset, ad esempio, `{{1, 2, 3}}`. Quando il multiset di wrapping contiene più elementi multiset, ad esempio `{{1, 2}, {3, 4}}`, non sono supportati valori letterali di multiset annidati.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore MULTISET per creare un'istanza di un multiset da un elenco di valori. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Vedere anche

- [Costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
