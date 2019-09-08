---
title: Esecuzione di query su dataset (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783040"
---
# <a name="querying-datasets-linq-to-dataset"></a>Esecuzione di query su dataset (LINQ to DataSet)
È possibile iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> dopo averlo popolato con i dati. La formulazione di query con LINQ to DataSet è simile [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] all'utilizzo [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]di su altre origini dati abilitate. Tenere presente, tuttavia, che quando si [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] utilizzano query su <xref:System.Data.DataSet> un oggetto si esegue una query su un' <xref:System.Data.DataRow> enumerazione di oggetti, anziché un'enumerazione di un tipo personalizzato. Ciò significa che è possibile usare qualsiasi membro della <xref:System.Data.DataRow> classe [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] nelle query. e creare query dettagliate e complesse.  
  
 Come per le altre implementazioni [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]di, è possibile creare query LINQ to DataSet in due formati diversi, ovvero la sintassi delle espressioni di query e la sintassi delle query basate su metodo. È possibile utilizzare la sintassi delle espressioni di query o la sintassi delle query basate su metodo per eseguire query su singole tabelle di <xref:System.Data.DataSet>, più tabelle di <xref:System.Data.DataSet> o tabelle di <xref:System.Data.DataSet> tipizzati.  
  
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
