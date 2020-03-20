---
title: Riferimento rapido a Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150350"
---
# <a name="entity-sql-quick-reference"></a>Riferimento rapido a Entity SQL
In questo argomento viene fornita una guida di riferimento rapido alle query [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Le query incluse in questo argomento sono basate sul modello Sales di AdventureWorks.  
  
## <a name="literals"></a>Valori letterali  
  
### <a name="string"></a>string  
 I valori letterali carattere di tipo String possono essere Unicode e non Unicode. Le stringhe Unicode vengono precedute da N. Ad esempio, `N'hello'`.  
  
 Di seguito è illustrato un esempio di valore letterale stringa Non-Unicode:  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 Output:  
  
|valore|  
|-----------|  
|hello|  
  
### <a name="datetime"></a>Datetime  
 Nei valori letterali di tipo DateTime sono obbligatorie sia la parte relativa alla data che quella relativa all'ora. Non sono previsti valori predefiniti.  
  
 Esempio:  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 Output:  
  
|valore|  
|-----------|  
|12/25/2006 1:01:00 AM|  
  
### <a name="integer"></a>Integer  
 I valori letterali Integer possono essere di tipo Int32 (123), UInt32 (123U), Int64 (123L) e UInt64 (123UL).  
  
 Esempio:  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 Output:  
  
|valore|  
|-----------|  
|1|  
|2|  
|3|  
  
### <a name="other"></a>Altri  
 Gli altri valori letterali supportati da [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono Guid, Binary, Float/Double, Decimal e `null`. I valori letterali Null in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono considerati compatibili con tutti i tipi ne modello concettuale.  
  
## <a name="type-constructors"></a>Costruttori di tipo  
  
### <a name="row"></a>ROW  
 [ROW](row-entity-sql.md) costruisce un valore (record) anonimo, strutturalmente tipizzato come in:`ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Esempio:  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 Output:  
  
|ProductID|Nome|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  
 [MULTISET](multiset-entity-sql.md) costruisce raccolte, ad esempio:  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 Esempio:  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Output:  
  
|ProductID|Nome|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>Oggetto  
 [Costrutti di costruttore](named-type-constructor-entity-sql.md) di tipi denominati `person("abc", 12)`(denominati) oggetti definiti dall'utente, ad esempio .  
  
 Esempio:  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 Output:  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>Riferimenti  
  
### <a name="ref"></a>REF  
 [REF](ref-entity-sql.md) crea un riferimento a un'istanza del tipo di entità. La query seguente restituisce ad esempio i riferimenti a ogni entità Order nel set di entità Orders:  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 Output:  
  
|valore|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 Nell'esempio seguente viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà di un'entità. Quando viene usato l'operatore di estrazione delle proprietà, il riferimento viene automaticamente dereferenziato.  
  
 Esempio:  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 Output:  
  
|valore|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  
 [DEREF](deref-entity-sql.md) dereferenzia un valore di riferimento e produce il risultato di tale dereferenziazione. La query seguente restituisce ad esempio le entità Order per ogni oggetto Order nel set di entità Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Esempio:  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 Output:  
  
|valore|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF e KEY  
 [CREATEREF](createref-entity-sql.md) crea un riferimento passando una chiave. [KEY](key-entity-sql.md) estrae la parte chiave di un'espressione con riferimento al tipo.  
  
 Esempio:  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 Output:  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## <a name="functions"></a>Funzioni  
  
### <a name="canonical"></a>Canonical  
 Lo spazio dei nomi per le `Edm.Length("string")` [funzioni canoniche](canonical-functions.md) è Edm, come in . Non è necessario specificare lo spazio dei nomi a meno che non venga importato un altro spazio dei nomi contenente una funzione con lo stesso nome della funzione canonica. Se due spazi dei nomi includono la stessa funzione, l'utente deve specificare il nome completo.  
  
 Esempio:  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 Output:  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### <a name="microsoft-provider-specific"></a>Specifiche del provider Microsoft  
 [Le funzioni specifiche](../sqlclient-for-ef-functions.md) del `SqlServer` provider Microsoft si trovano nello spazio dei nomi .  
  
 Esempio:  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 Output:  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## <a name="namespaces"></a>Spazi dei nomi  
 [USING](using-entity-sql.md) specifica gli spazi dei nomi utilizzati in un'espressione di query.  
  
 Esempio:  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 Output:  
  
|valore|  
|-----------|  
|aa|  
  
## <a name="paging"></a>Paging  
 Il paging può essere espresso dichiarando una sottoclausola [SKIP](skip-entity-sql.md) e [LIMIT](limit-entity-sql.md) alla clausola [ORDER BY.](order-by-entity-sql.md)  
  
 Esempio:  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Output:  
  
|ID|Nome|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>Raggruppamento  
 [GROUPING BY](group-by-entity-sql.md) specifica i gruppi in cui devono essere inseriti gli oggetti restituiti da un'espressione di query ([SELECT](select-entity-sql.md)).  
  
 Esempio:  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 Output:  
  
|name|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## <a name="navigation"></a>Navigazione  
 L' operatore di navigazione delle relazioni consente di eseguire la navigazione in una relazione da un'entità (entità finale di origine) a un'altra (entità finale di destinazione). [NAVIGATE](navigate-entity-sql.md) accetta il tipo \<di relazione qualificato come> dello spazio dei nomi. \<> del nome del tipo di relazione. Navigate restituisce Ref\<T> se la cardinalità della fine alla fine è 1. Se la cardinalità della fine di fine\<è n, verrà restituita la raccolta<>> Ref T.  
  
 Esempio:  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 Output:  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## <a name="select-value-and-select"></a>SELECT VALUE e SELECT  
  
### <a name="select-value"></a>SELECT VALUE  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce la clausola SELECT VALUE per consentire di ignorare la costruzione di riga implicita. In una clausola SELECT VALUE può essere specificato un solo elemento. Quando viene utilizzata una clausola di questo tipo, non viene costruito alcun wrapper di riga intorno `SELECT VALUE a`agli elementi nella clausola SELECT ed è possibile produrre una raccolta della forma desiderata, ad esempio: .  
  
 Esempio:  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 Output:  
  
|Nome|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>SELECT  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce inoltre il costruttore ROW per la costruzione di righe arbitrarie. SELECT accetta uno o più elementi nella proiezione e restituisce un record di dati con campi, ad esempio `SELECT a, b, c`.  
  
 Esempio:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:  
  
|Nome|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>Espressione CASE  
 [L'espressione case](case-entity-sql.md) valuta un set di espressioni booleane per determinare il risultato.  
  
 Esempio:  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Output:  
  
|valore|  
|-----------|  
|TRUE|  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Cenni preliminari su Entity SQL](entity-sql-overview.md)
