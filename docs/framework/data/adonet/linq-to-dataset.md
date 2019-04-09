---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 92be418e38039757437e6e673f39a7baef011528
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221782"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] rende più semplice e rapido per eseguire query sui dati memorizzati nella cache un <xref:System.Data.DataSet> oggetto. In particolare, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] semplifica l'esecuzione di query, consentendo agli sviluppatori di scrivere query dal linguaggio di programmazione stesso, anziché tramite un linguaggio di query separata. Ciò è particolarmente utile per gli sviluppatori di Visual Studio, che possono ora sfruttare i vantaggi del controllo della sintassi in fase di compilazione, tipizzazione statica e supporto IntelliSense resi disponibili da Visual Studio nelle query.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] può anche essere usato per eseguire query su dati che sono stati consolidati da una o più origini dati. In tal modo sono possibili molti scenari in cui è necessario rappresentare e gestire i dati con flessibilità, ad esempio per le query su dati aggregati localmente e la memorizzazione nella cache di livello intermedio nelle applicazioni Web. In particolare, questo tipo di modifiche sono richieste nelle applicazioni generiche per la creazione di rapporti, di analisi e di Business Intelligence.  
  
 Il [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] la funzionalità è esposta principalmente tramite i metodi di estensione nel <xref:System.Data.DataRowExtensions> e <xref:System.Data.DataTableExtensions> classi. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] si basa sul e Usa esistente [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architettura e non è destinato a sostituire [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] nel codice dell'applicazione. Il codice ADO.NET 2.0 esistente continuerà a funzionare nelle applicazioni [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Nel diagramma seguente viene illustrata la relazione tra [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] e  [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] e l'archivio dati.  
  
 ![Diagramma che mostra che LINQ to DataSet è basato sul provider ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Vedere anche

- [Language-Integrated Query (LINQ)-C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ e ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
