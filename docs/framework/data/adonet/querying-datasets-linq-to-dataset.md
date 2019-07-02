---
title: Esecuzione di query su dataset (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: ec4ee345835294499f7ac9f665a9b79e2efc0f64
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504659"
---
# <a name="querying-datasets-linq-to-dataset"></a>Esecuzione di query su dataset (LINQ to DataSet)
È possibile iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> dopo averlo popolato con i dati. La formulazione di query con LINQ to DataSet è simile all'uso [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] su altre [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-origini dati. È tuttavia importante ricordare che quando si usa [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] esegue una query su una <xref:System.Data.DataSet> sottoposte a query un'enumerazione dell'oggetto <xref:System.Data.DataRow> oggetti, invece di un'enumerazione di un tipo personalizzato. Ciò significa che è possibile usare uno qualsiasi dei membri del <xref:System.Data.DataRow> classe di [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] le query. e creare query dettagliate e complesse.  
  
 Come con altre implementazioni di [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], è possibile creare LINQ alle query di set di dati in due formati diversi: espressione sintassi delle query e sintassi di query basate su metodo. È possibile utilizzare la sintassi delle espressioni di query o la sintassi delle query basate su metodo per eseguire query su singole tabelle di <xref:System.Data.DataSet>, più tabelle di <xref:System.Data.DataSet> o tabelle di <xref:System.Data.DataSet> tipizzati.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Query su singola tabella](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Viene descritto come eseguire query su una singola tabella.  
  
 [Query su tabella incrociata](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Viene descritto come eseguire query tra tabelle.  
  
 [Esecuzione di query su oggetti DataSet tipizzati](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet> tipizzati.  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [Caricamento di dati in un oggetto DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
