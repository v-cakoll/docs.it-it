---
title: Esecuzione di query su dataset (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: bb64abcffdbbcd46dfb11b2564619c565e461436
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634781"
---
# <a name="querying-datasets-linq-to-dataset"></a>Esecuzione di query su dataset (LINQ to DataSet)
È possibile iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> dopo averlo popolato con i dati. La formulazione di query con LINQ to DataSet è simile all'utilizzo di LINQ (Language-Integrated Query) rispetto ad altre origini dati abilitate per LINQ. Tenere presente, tuttavia, che quando si usano query LINQ su un oggetto <xref:System.Data.DataSet>, si sta eseguendo una query su un'enumerazione di oggetti <xref:System.Data.DataRow> invece che su un'enumerazione di un tipo personalizzato. Ciò significa che è possibile usare qualsiasi membro della classe <xref:System.Data.DataRow> nelle query LINQ. In questo modo è possibile creare query complesse e complesse.  
  
 Come per le altre implementazioni di LINQ, è possibile creare query LINQ to DataSet in due formati diversi, ovvero la sintassi delle espressioni di query e la sintassi delle query basate su metodo. È possibile utilizzare la sintassi delle espressioni di query o la sintassi delle query basate su metodo per eseguire query su singole tabelle di <xref:System.Data.DataSet>, più tabelle di <xref:System.Data.DataSet> o tabelle di <xref:System.Data.DataSet> tipizzati.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Query su singola tabella](single-table-queries-linq-to-dataset.md)  
 Viene descritto come eseguire query su una singola tabella.  
  
 [Query su tabella incrociata](cross-table-queries-linq-to-dataset.md)  
 Viene descritto come eseguire query tra tabelle.  
  
 [Esecuzione di query su oggetti DataSet tipizzati](querying-typed-datasets.md)  
 Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet> tipizzati.  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di LINQ to DataSet](linq-to-dataset-examples.md)
- [Caricamento di dati in un oggetto DataSet](loading-data-into-a-dataset.md)
