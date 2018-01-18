---
title: Mapping basato su attributi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dd89999-f415-4d61-b8c8-237d23d7924e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a7a66b165e5bcfc605842b96295ae1721e7b3af5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="attribute-based-mapping"></a>Mapping basato su attributi
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]esegue il mapping di un database di SQL Server per un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti applicando attributi o utilizzando un file di mapping esterno. In questo argomento viene descritto l'approccio basato sugli attributi.  
  
 Nella forma più elementare, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping di un database a un oggetto <xref:System.Data.Linq.DataContext>, di una tabella a una classe e di colonne e relazioni alle proprietà in tali classi. È anche possibile usare attributi per eseguire il mapping di una gerarchia di ereditarietà nel modello a oggetti. Per ulteriori informazioni, vedere [procedura: generare il modello a oggetti in Visual Basic o c#](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
 Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] in genere eseguono il mapping basato sugli attributi tramite il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. È anche possibile usare lo strumento da riga di comando SQLMetal o codificare gli attributi manualmente. Per ulteriori informazioni, vedere [procedura: generare il modello a oggetti in Visual Basic o c#](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
> [!NOTE]
>  Il mapping può inoltre essere eseguito usando un file XML esterno. Per ulteriori informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
 Nelle sezioni seguenti viene descritto in dettaglio il mapping basato sugli attributi. Per altre informazioni, vedere lo spazio dei nomi <xref:System.Data.Linq.Mapping>.  
  
## <a name="databaseattribute-attribute"></a>Attributo DatabaseAttribute  
 Usare questo attributo per specificare il nome predefinito del database quando non viene fornito un nome dalla connessione. Questo attributo è facoltativo, ma se viene usato è necessario applicare la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>, come descritto nella tabella seguente.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>|String|Vedere <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>|Usato con la relativa proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>, consente di specificare il nome del database.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
## <a name="tableattribute-attribute"></a>Attributo TableAttribute  
 Usare questo attributo per definire una classe come classe dell'entità associata a una visualizzazione o tabella di database. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le classi con questo attributo vengono gestite come classi persistenti. La tabella seguente descrive la proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>|String|Stessa stringa del nome della classe|Consente di definire una classe come classe dell'entità associata a una tabella di database.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
## <a name="columnattribute-attribute"></a>Attributo ColumnAttribute  
 Usare questo attributo per definire un membro di una classe dell'entità per rappresentare una colonna in una tabella di database. È possibile applicare questo attributo a qualsiasi campo o proprietà.  
  
 Solo i membri identificati come colonne vengono recuperati e resi persistenti quando le modifiche al database vengono salvate da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. I membri privi di questo attributo vengono considerati non persistenti e non vengono inviati per inserimenti o aggiornamenti.  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>|AutoSync|Never|Indica a Common Language Runtime (CLR) di recuperare il valore dopo un'operazione di inserimento o di aggiornamento.<br /><br /> Opzioni: Always, Never, OnUpdate, OnInsert.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>|Boolean|`true`|Indica che una colonna può contenere valori null.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>|String|Tipo di colonna di database dedotto|Consente di usare tipi di database e modificatori per specificare il tipo di colonna del database.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>|String|Empty|Consente di definire una colonna calcolata in un database.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>|Boolean|`false`|Consente di indicare che una colonna contiene valori generati automaticamente dal database.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>|Boolean|`false`|Consente di indicare che la colonna contiene un valore discriminante per una gerarchia di ereditarietà di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>|Boolean|`false`|Consente di specificare che questo membro della classe rappresenta una colonna che corrisponde o fa parte delle chiavi primarie della tabella.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>|Boolean|`false`|Consente di identificare il tipo di colonna del membro come un timestamp del database o un numero di versione.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>|UpdateCheck|`Always`, a meno che, per un membro, <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> sia `true`|Consente di specificare l'approccio adottato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per il rilevamento dei conflitti di concorrenza ottimistici.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
> [!NOTE]
>  I valori delle proprietà di archiviazione AssociationAttribute e ColumnAttribute rispettano la distinzione tra maiuscole e minuscole. Verificare, ad esempio, che per i valori dell'attributo della proprietà AssociationAttribute.Storage venga usata la stessa combinazione di maiuscole e minuscole adoperata per i nomi di proprietà corrispondenti usati in altri punti del codice. Ciò si applica a tutti i linguaggi di programmazione .NET, anche a quelli che in genere non distinguono tra maiuscole e minuscole, tra cui [!INCLUDE[vb_current_short](../../../../../../includes/vb-current-short-md.md)]. Per altre informazioni sulla proprietà di archiviazione, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="associationattribute-attribute"></a>Attributo AssociationAttribute  
 Usare questo attributo per definire una proprietà che rappresenti un'associazione nel database, ad esempio una relazione da chiave esterna a chiave primaria. Per ulteriori informazioni sulle relazioni, vedere [procedura: mappare le relazioni di Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md).  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteOnNull%2A>|Boolean|`false`|Quando viene inserita in un'associazione i cui membri della chiave esterna sono tutti non nullable, consente di eliminare l'oggetto quando l'associazione viene impostata su null.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteRule%2A>|String|None|Consente di aggiungere il comportamento di eliminazione a un'associazione.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsForeignKey%2A>|Boolean|`false`|Se è impostata su True, consente di definire il membro come chiave esterna in un'associazione che rappresenta una relazione di database.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsUnique%2A>|Boolean|`false`|Se è impostata su True, indica un vincolo di univocità sulla chiave esterna.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>|String|ID della classe correlata|Consente di definire uno o più membri della classe dell'entità di destinazione come valori delle chiavi sull'altro lato dell'associazione.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.ThisKey%2A>|String|ID della classe che contiene la proprietà|Consente di definire i membri della classe di questa entità per rappresentare i valori delle chiavi su questo lato dell'associazione.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.AssociationAttribute>.  
  
> [!NOTE]
>  I valori delle proprietà di archiviazione AssociationAttribute e ColumnAttribute rispettano la distinzione tra maiuscole e minuscole. Verificare, ad esempio, che per i valori dell'attributo della proprietà AssociationAttribute.Storage venga usata la stessa combinazione di maiuscole e minuscole adoperata per i nomi di proprietà corrispondenti usati in altri punti del codice. Ciò si applica a tutti i linguaggi di programmazione .NET, anche a quelli che in genere non distinguono tra maiuscole e minuscole, tra cui [!INCLUDE[vb_current_short](../../../../../../includes/vb-current-short-md.md)]. Per altre informazioni sulla proprietà di archiviazione, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="inheritancemappingattribute-attribute"></a>Attributo InheritanceMappingAttribute  
 Usare questo attributo per eseguire il mapping di una gerarchia di ereditarietà.  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>|String|Nessuno. È necessario specificare un valore.|Consente di specificare il valore del codice del discriminatore.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>|Boolean|`false`|Se è impostata su True, consente di creare un'istanza di un oggetto di questo tipo quando nessun valore discriminante nell'archivio corrisponde a uno dei valori specificati.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>|Tipo|Nessuno. È necessario specificare un valore.|Consente di specificare il tipo della classe nella gerarchia.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>.  
  
## <a name="functionattribute-attribute"></a>Attributo FunctionAttribute   
 Usare questo attributo per definire un metodo che rappresenti una stored procedure o una funzione definita dall'utente nel database.  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>|Boolean|`false`|Se è impostata su false, indica il mapping a una stored procedure. Se è impostata su True, indica il mapping a una funzione definita dall'utente.|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.Name%2A>|String|La stessa stringa del nome nel database|Consente di specificare il nome della stored procedure o della funzione definita dall'utente.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.FunctionAttribute>.  
  
## <a name="parameterattribute-attribute"></a>Attributo ParameterAttribute  
 Usare questo attributo per eseguire il mapping dei parametri di input ai metodi della stored procedure.  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.DbType%2A>|String|None|Consente di specificare il tipo di database.|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.Name%2A>|String|Stessa stringa del nome di parametro nel database|Consente di specificare un nome per il parametro.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ParameterAttribute>.  
  
## <a name="resulttypeattribute-attribute"></a>Attributo ResultTypeAttribute  
 Usare questo attributo per specificare un tipo di risultato.  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ResultTypeAttribute.Type%2A>|Tipo|(Nessuno)|Usata per i metodi di cui è stato eseguito il mapping a stored procedure che restituiscono <xref:System.Data.Linq.IMultipleResults>. Consente di dichiarare i mapping dei tipi validi o previsti per la stored procedure.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ResultTypeAttribute>.  
  
## <a name="dataattribute-attribute"></a>Attributo DataAttribute  
 Usare questo attributo per specificare nomi e campi di archiviazione privati.  
  
 La tabella seguente descrive le proprietà di questo attributo.  
  
|Proprietà|Tipo|Default|Descrizione|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>|String|Stessa stringa del nome nel database|Consente di specificare il nome della tabella, della colonna e così via.|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>|String|Funzioni di accesso pubbliche|Consente di specificare il nome del campo di archiviazione sottostante.|  
  
 Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.DataAttribute>.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
