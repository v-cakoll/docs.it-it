---
title: Aggiunta di un oggetto DataTable a un dataset
description: Vedere questo codice di esempio per informazioni su come creare oggetti DataTable e aggiungerli a un set di dati esistente in ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 42bd36b394de560884a2ec607f4cbc65d1171e4e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286960"
---
# <a name="adding-a-datatable-to-a-dataset"></a>Aggiunta di un oggetto DataTable a un dataset
ADO.NET consente di creare oggetti <xref:System.Data.DataTable> e di aggiungerli a un tipo <xref:System.Data.DataSet> esistente. È possibile impostare le informazioni relative ai vincoli per un tipo <xref:System.Data.DataTable> usando le proprietà <xref:System.Data.DataTable.PrimaryKey%2A> e <xref:System.Data.DataColumn.Unique%2A>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente consente di creare un tipo <xref:System.Data.DataSet>, aggiungere un nuovo oggetto <xref:System.Data.DataTable> al <xref:System.Data.DataSet> e aggiungere tre oggetti <xref:System.Data.DataColumn> alla tabella. Il codice consente infine di impostare una colonna come colonna di chiave primaria.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Maiuscole/minuscole  
 In un tipo <xref:System.Data.DataSet> sono consentite due o più tabelle o relazioni con lo stesso nome ma con diversa combinazione di maiuscole e minuscole. In questi casi, i riferimenti basati sui nomi a tabelle e relazioni prevedono la distinzione tra maiuscole e minuscole. Se, ad esempio, il <xref:System.Data.DataSet> **set di dati** contiene tabelle **Tabella1** e **Tabella1**, è necessario fare riferimento a **Tabella1** in base al nome come **DataSet. Tables ["Tabella1"]** e **Tabella1** come **DataSet. Tables ["Tabella1"]**. Il tentativo di fare riferimento a una delle tabelle come **DataSet. Tables ["Tabella1"]** genererebbe un'eccezione.  
  
 La distinzione tra maiuscole e minuscole non è rilevante se è presente solo una tabella o relazione con un determinato nome. Se, ad esempio, <xref:System.Data.DataSet> ha solo **Tabella1**, è possibile farvi riferimento utilizzando **DataSet. Tables ["Tabella1"]**.  
  
> [!NOTE]
> La proprietà <xref:System.Data.DataSet.CaseSensitive%2A> del tipo <xref:System.Data.DataSet> non influisce su tale comportamento. La proprietà <xref:System.Data.DataSet.CaseSensitive%2A> viene infatti applicata ai dati del tipo <xref:System.Data.DataSet> e influisce sull'ordinamento, la ricerca, l'applicazione di filtri, di vincoli e così via.  
  
## <a name="namespace-support"></a>Supporto dello spazio dei nomi  
 Nelle versioni ADO.NET precedenti alla 2.0 due tabelle non potevano avere lo stesso nome, anche se si trovavano in spazi dei nomi diversi. In ADO.NET 2.0 questa limitazione è stata eliminata. Un tipo <xref:System.Data.DataSet> può contenere due tabelle con lo stesso valore per la proprietà <xref:System.Data.DataTable.TableName%2A> ma con valori diversi per la proprietà <xref:System.Data.DataTable.Namespace%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
