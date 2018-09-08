---
title: Vincoli DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: fa70af311d6b4fa4e17bb3ba6110e4cea420c34c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200288"
---
# <a name="datatable-constraints"></a>Vincoli DataTable
I vincoli consentono di applicare restrizioni ai dati di una <xref:System.Data.DataTable>, in modo da garantire l'integrità di tali dati. Un vincolo è una regola automatica applicata a una colonna, o a colonne correlate, che consente di determinare le operazioni da eseguire in caso di modifica del valore di una riga. I vincoli vengono applicati quando le `System.Data.DataSet.EnforceConstraints` proprietà del <xref:System.Data.DataSet> viene **true**. Per un esempio di codice che illustra come impostare la proprietà `EnforceConstraints`, vedere l'argomento relativo a <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 In ADO.NET sono disponibili due tipi di vincoli: <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint>. Per impostazione predefinita, entrambi i vincoli vengono creati automaticamente quando si crea una relazione tra due o più tabelle aggiungendo un <xref:System.Data.DataRelation> per il **set di dati**. Tuttavia, è possibile disabilitare questo comportamento specificando **createConstraints** = **false** durante la creazione della relazione.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 Oggetto **ForeignKeyConstraint** impone le regole sulla modalità di propagazione degli aggiornamenti ed eliminazioni alle tabelle correlate. Ad esempio, se un valore in una riga di una tabella viene aggiornato o eliminato e lo stesso valore viene usato anche in uno o più tabelle correlate, un **ForeignKeyConstraint** determina ciò che accade nelle tabelle correlate.  
  
 Il <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> e <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> delle proprietà delle **ForeignKeyConstraint** definire l'azione da intraprendere quando l'utente tenta di eliminare o aggiornare una riga in una tabella correlata. La tabella seguente descrive le diverse impostazioni disponibili per il **DeleteRule** e **UpdateRule** le proprietà del **ForeignKeyConstraint**.  
  
|Impostazione della regola|Descrizione|  
|------------------|-----------------|  
|**Cascade**|Elimina o aggiorna righe correlate.|  
|**SetNull**|Impostare i valori nelle righe correlate **DBNull**.|  
|**SetDefault**|Imposta i valori delle righe correlate sul valore predefinito.|  
|**None**|Non viene eseguita alcuna operazione sulle righe correlate. Questa è l'impostazione predefinita.|  
  
 Oggetto **ForeignKeyConstraint** consente di limitare, oltre che propagare, le modifiche apportate a colonne correlate. A seconda delle proprietà impostate per il **ForeignKeyConstraint** di una colonna, se il **EnforceConstraints** proprietà del **set di dati** è **true**, eseguire determinate operazioni sulla riga padre comporterà un'eccezione. Ad esempio, se il **DeleteRule** proprietà del **ForeignKeyConstraint** viene **None**, una riga padre non può essere eliminata se dispone di tutte le righe figlio.  
  
 È possibile creare un vincolo di chiave esterna tra le singole colonne o una matrice di colonne usando il **ForeignKeyConstraint** costruttore. Passare l'oggetto risultante **ForeignKeyConstraint** dell'oggetto per il **Add** metodo per la tabella **vincoli** proprietà, ovvero un **ConstraintCollection**. È anche possibile passare gli argomenti del costruttore a diversi overload del **Add** metodo di un **ConstraintCollection** per creare un **ForeignKeyConstraint**.  
  
 Durante la creazione di un **ForeignKeyConstraint**, è possibile passare il **DeleteRule** e **UpdateRule** valori al costruttore come argomenti o è possono impostarli come proprietà come il in seguito esempio (in cui il **DeleteRule** è impostato su **None**).  
  
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
 Le modifiche alle righe possono essere accettate utilizzando il **AcceptChanges** metodo o annullato utilizzando il **RejectChanges** metodo del **set di dati**, **DataTable**, oppure **DataRow**. Quando un **set di dati** contiene **ForeignKeyConstraints**, la chiamata di **AcceptChanges** oppure **RejectChanges** metodi impone il  **AcceptRejectRule**. Il **AcceptRejectRule** proprietà delle **ForeignKeyConstraint** determina quali azioni saranno eseguite sull'elemento figlio delle righe quando **AcceptChanges** o  **RejectChanges** viene chiamato sulla riga padre.  
  
 La tabella seguente elenca le impostazioni disponibili per il **AcceptRejectRule**.  
  
|Impostazione della regola|Descrizione|  
|------------------|-----------------|  
|**Cascade**|Consente di accettare o rifiutare le modifiche alle righe figlio.|  
|**None**|Non viene eseguita alcuna operazione sulle righe figlio. Questa è l'impostazione predefinita.|  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.ForeignKeyConstraint>, ne vengono impostate alcune proprietà, tra cui <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, nonché viene aggiunto all'oggetto <xref:System.Data.ConstraintCollection> di un oggetto <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 Il **UniqueConstraint** oggetto, che può essere assegnato a una singola colonna o a una matrice di colonne in un **DataTable**, assicura che tutti i dati della colonna specificata o le colonne sia univoco per ogni riga. È possibile creare un vincolo unique per una colonna o una matrice di colonne usando il **UniqueConstraint** costruttore. Passare l'oggetto risultante **UniqueConstraint** dell'oggetto per il **Add** metodo per la tabella **vincoli** proprietà, ovvero un **ConstraintCollection**. È anche possibile passare gli argomenti del costruttore a diversi overload del **Add** metodo di un **ConstraintCollection** per creare un **UniqueConstraint**. Quando si crea una **UniqueConstraint** per una o più colonne, è possibile, facoltativamente, specificare se le colonne sono una chiave primaria.  
  
 È anche possibile creare un vincolo unique per una colonna impostando il **Unique** proprietà della colonna **true**. In alternativa, impostando il **Unique** proprietà di una singola colonna per **false** rimuove qualsiasi vincolo unique che potrebbe esistere. La definizione di una o più colonne come chiave primaria per una tabella consentirà di creare automaticamente un vincolo univoco per la colonna o le colonne specificate. Se si rimuove una colonna dal **PrimaryKey** proprietà di un **DataTable**, il **UniqueConstraint** viene rimosso.  
  
 L'esempio seguente crea una **UniqueConstraint** per due colonne di una **DataTable**.  
  
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
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
