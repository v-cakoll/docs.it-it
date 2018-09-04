---
title: Aggiunta di un oggetto DataTable a un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 5f2282b7aea8adf9e7574e2abe86af7cc5a487e8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505921"
---
# <a name="adding-a-datatable-to-a-dataset"></a>Aggiunta di un oggetto DataTable a un dataset
ADO.NET consente di creare oggetti <xref:System.Data.DataTable> e di aggiungerli a un tipo <xref:System.Data.DataSet> esistente. È possibile impostare le informazioni relative ai vincoli per un tipo <xref:System.Data.DataTable> usando le proprietà <xref:System.Data.DataTable.PrimaryKey%2A> e <xref:System.Data.DataColumn.Unique%2A>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente consente di creare un tipo <xref:System.Data.DataSet>, aggiungere un nuovo oggetto <xref:System.Data.DataTable> al <xref:System.Data.DataSet> e aggiungere tre oggetti <xref:System.Data.DataColumn> alla tabella. Il codice consente infine di impostare una colonna come colonna di chiave primaria.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Distinzione fra maiuscole e minuscole  
 In un tipo <xref:System.Data.DataSet> sono consentite due o più tabelle o relazioni con lo stesso nome ma con diversa combinazione di maiuscole e minuscole. In questi casi, i riferimenti basati sui nomi a tabelle e relazioni prevedono la distinzione tra maiuscole e minuscole. Ad esempio, se il <xref:System.Data.DataSet> **set di dati** contiene tabelle **Table1** e **table1**, si fa riferimento a **Table1** con nome **dataSet.Tables["Table1"]**, e **table1** come **dataSet.Tables["table1"]**. Tentativo di fare riferimento a una delle tabelle come **dataSet.Tables["TABLE1"]** verrà generata un'eccezione.  
  
 La distinzione tra maiuscole e minuscole non è rilevante se è presente solo una tabella o relazione con un determinato nome. Ad esempio, se il <xref:System.Data.DataSet> contiene solo **Table1**, è possibile farvi riferimento usando **dataSet.Tables["TABLE1"]**.  
  
> [!NOTE]
>  La proprietà <xref:System.Data.DataSet.CaseSensitive%2A> del tipo <xref:System.Data.DataSet> non influisce su tale comportamento. La proprietà <xref:System.Data.DataSet.CaseSensitive%2A> viene infatti applicata ai dati del tipo <xref:System.Data.DataSet> e influisce sull'ordinamento, la ricerca, l'applicazione di filtri, di vincoli e così via.  
  
## <a name="namespace-support"></a>Supporto dello spazio dei nomi  
 Nelle versioni ADO.NET precedenti alla 2.0 due tabelle non potevano avere lo stesso nome, anche se si trovavano in spazi dei nomi diversi. In ADO.NET 2.0 questa limitazione è stata eliminata. Un tipo <xref:System.Data.DataSet> può contenere due tabelle con lo stesso valore per la proprietà <xref:System.Data.DataTable.TableName%2A> ma con valori diversi per la proprietà <xref:System.Data.DataTable.Namespace%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
