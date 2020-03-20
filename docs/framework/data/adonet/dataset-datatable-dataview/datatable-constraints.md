---
title: Vincoli DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151286"
---
# <a name="datatable-constraints"></a>Vincoli DataTable
I vincoli consentono di applicare restrizioni ai dati di una <xref:System.Data.DataTable>, in modo da garantire l'integrità di tali dati. Un vincolo è una regola automatica applicata a una colonna, o a colonne correlate, che consente di determinare le operazioni da eseguire in caso di modifica del valore di una riga. I vincoli vengono `System.Data.DataSet.EnforceConstraints` applicati <xref:System.Data.DataSet> quando la proprietà dell'oggetto è **true**. Per un esempio di codice che illustra come impostare la proprietà `EnforceConstraints`, vedere l'argomento relativo a <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 In ADO.NET sono disponibili due tipi di vincoli: <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint>. Per impostazione predefinita, entrambi i vincoli vengono creati automaticamente <xref:System.Data.DataRelation> quando si crea una relazione tra due o più tabelle aggiungendo un oggetto al **DataSet**. Tuttavia, è possibile disabilitare questo comportamento specificando **createConstraints** = **false** durante la creazione della relazione.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 Oggetto **ForeignKeyConstraint** applica regole su come vengono propagati gli aggiornamenti e le eliminazioni alle tabelle correlate. Ad esempio, se un valore in una riga di una tabella viene aggiornato o eliminato e lo stesso valore viene utilizzato anche in una o più tabelle correlate, un **ForeignKeyConstraint** determina ciò che accade nelle tabelle correlate.  
  
 Le <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> proprietà e di **ForeignKeyConstraint** definiscono l'azione da eseguire quando l'utente tenta di eliminare o aggiornare una riga in una tabella correlata. Nella tabella seguente vengono descritte le diverse impostazioni disponibili per le proprietà **DeleteRule** e **UpdateRule** di **ForeignKeyConstraint**.  
  
|Impostazione della regola|Descrizione|  
|------------------|-----------------|  
|**Cascata**|Elimina o aggiorna righe correlate.|  
|**SetNull**|Impostare i valori nelle righe correlate su **DBNull**.|  
|**SetDefault**|Imposta i valori delle righe correlate sul valore predefinito.|  
|**Nessuno**|Non viene eseguita alcuna operazione sulle righe correlate. Questa è la modalità predefinita.|  
  
 Oggetto **ForeignKeyConstraint** può limitare, nonché propagare, le modifiche alle colonne correlate. A seconda delle proprietà impostate per **il ForeignKeyConstraint** di una colonna, se il **EnforceConstraints** proprietà del **DataSet** è **true**, l'esecuzione di determinate operazioni sulla riga padre genererà un'eccezione. Ad esempio, se la proprietà **DeleteRule** di **ForeignKeyConstraint** è **None**, una riga padre non può essere eliminata se contiene righe figlio.  
  
 È possibile creare un vincolo di chiave esterna tra singole colonne o tra una matrice di colonne utilizzando il **ForeignKeyConstraint** costruttore. Passare l'oggetto **ForeignKeyConstraint** risultante al metodo **Add** della proprietà **Constraints** della tabella, che è un **oggetto ConstraintCollection**. È inoltre possibile passare argomenti del costruttore a diversi overload del metodo **Add** di un **oggetto ConstraintCollection** per creare un **oggetto ForeignKeyConstraint**.  
  
 Quando si crea un **ForeignKeyConstraint**, è possibile passare i valori **DeleteRule** e **UpdateRule** al costruttore come argomenti oppure impostarli come proprietà come nell'esempio seguente (in cui il valore **DeleteRule** è impostato su **None**).  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  
 Le modifiche alle righe possono essere accettate utilizzando il metodo **AcceptChanges** o annullate utilizzando il metodo **RejectChanges** di **DataSet**, **DataTable**o **DataRow**. Quando un **DataSet** contiene **ForeignKeyConstraints**, la chiamata dei metodi **AcceptChanges** o **RejectChanges** applica l'oggetto **AcceptRejectRule**. La proprietà **AcceptRejectRule** di **ForeignKeyConstraint** determina quale azione verrà eseguita sulle righe figlio quando **AcceptChanges** o **RejectChanges** vengono chiamati sulla riga padre.  
  
 Nella tabella seguente sono elencate le impostazioni disponibili per **AcceptRejectRule**.  
  
|Impostazione della regola|Descrizione|  
|------------------|-----------------|  
|**Cascata**|Consente di accettare o rifiutare le modifiche alle righe figlio.|  
|**Nessuno**|Non viene eseguita alcuna operazione sulle righe figlio. Questa è la modalità predefinita.|  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.ForeignKeyConstraint>, ne vengono impostate alcune proprietà, tra cui <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, nonché viene aggiunto all'oggetto <xref:System.Data.ConstraintCollection> di un oggetto <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 L'oggetto **UniqueConstraint,** che può essere assegnato a una singola colonna o a una matrice di colonne in un **oggetto DataTable**, garantisce che tutti i dati nella colonna o nelle colonne specificate siano univoci per riga. È possibile creare un vincolo univoco per una colonna o una matrice di colonne utilizzando il **UniqueConstraint** costruttore. Passare l'oggetto **UniqueConstraint** risultante al metodo **Add** della proprietà **Constraints** della tabella, che è un **oggetto ConstraintCollection**. È inoltre possibile passare argomenti del costruttore a diversi overload del metodo **Add** di un **oggetto ConstraintCollection** per creare un **oggetto UniqueConstraint**. Quando si crea un **UniqueConstraint** per una o più colonne, è possibile specificare se la colonna o le colonne sono una chiave primaria.  
  
 È inoltre possibile creare un vincolo univoco per una colonna impostando la proprietà **Unique** della colonna **su true**. In alternativa, l'impostazione della proprietà **Unique** di una singola colonna su **false** rimuove qualsiasi vincolo univoco esistente. La definizione di una o più colonne come chiave primaria per una tabella consentirà di creare automaticamente un vincolo univoco per la colonna o le colonne specificate. Se si rimuove una colonna dalla proprietà **PrimaryKey** di un **oggetto DataTable**, il **UniqueConstraint** viene rimosso.  
  
 Nell'esempio seguente viene creato un **oggetto UniqueConstraint** per due colonne di un oggetto **DataTable**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [Definizione dello schema DataTable](datatable-schema-definition.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
