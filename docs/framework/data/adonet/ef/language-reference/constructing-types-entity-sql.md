---
title: Costruzione di tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: 91ed123132965353ff354282f6850e9ef9cba3d0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765256"
---
# <a name="constructing-types-entity-sql"></a>Costruzione di tipi (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono disponibili tre tipi di costruttori: costruttori di riga, costruttori di tipi denominati e i costruttori di raccolte.  
  
## <a name="row-constructors"></a>Costruttori di riga  
 I costruttori di riga vengono usati in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per costruire record anonimi e con strutture tipizzate da uno o più valori. Il tipo di risultato di un costruttore di riga è un tipo di riga i cui tipi di campo corrispondono ai tipi dei valori usati per costruire la riga. Ad esempio, l'espressione seguente viene creato un valore di tipo `Record(a int, b string, c int)`:  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 Se non si fornisce un alias per un'espressione in un costruttore di riga, in Entity Framework viene eseguito un tentativo di generarne uno. Per ulteriori informazioni, vedere la sezione "Regole di Aliasing" in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Le regole seguenti riguardano l'uso di alias nelle espressioni in un costruttore di riga:  
  
-   Le espressioni in un costruttore ROW non possono fare riferimento ad altri alias nello stesso costruttore.  
  
-   Due espressioni nello stesso costruttore di riga non possono avere lo stesso alias.  
  
 Per ulteriori informazioni sui costruttori di riga, vedere [riga](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="collection-constructors"></a>Costruttori di raccolte  
 I costruttori di raccolte vengono usati in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per creare un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore devono essere di tipo `T` reciprocamente compatibile e il costruttore produce una raccolta di tipo `Multiset<T>`. L'espressione seguente consente ad esempio di creare una raccolta di valori interi:  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 I costruttori multiset vuoti non sono supportati perché non è possibile determinare il tipo degli elementi. Il codice seguente non è valido:  
  
 `multiset() {}`  
  
 Per ulteriori informazioni, vedere [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).  
  
## <a name="named-type-constructors-namedtype-initializers"></a>Costruttori di tipi denominati (inizializzatori NamedType)  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] i costruttori di tipi (inizializzatori) possono creare istanze di tipi di entità e di tipi complessi denominati. L'espressione seguente consente ad esempio di creare un'istanza di un tipo `Person`.  
  
 `Person("abc", 12)`  
  
 L'espressione seguente consente di creare un'istanza di un tipo complesso.  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 L'espressione seguente consente di creare un'istanza di un tipo complesso annidato.  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 L'espressione seguente consente di creare un'istanza di un'entità con un tipo complesso annidato.  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 Nell'esempio seguente viene illustrato come inizializzare una proprietà di un tipo complesso impostandola su Null. `MyModel.ZipCode(‘98118’, null)`  
  
 Si suppone che gli argomenti del costruttore si trovino nello stesso ordine della dichiarazione degli attributi del tipo.  
  
 Per ulteriori informazioni, vedere [costruttore di tipo denominato](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)
