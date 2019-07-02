---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: c4069ef760877935c4ce194144d131d0dc58b4d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504359"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
LINQ to DataSet rende più semplice e veloce eseguire una query sui dati memorizzati nella cache in un <xref:System.Data.DataSet> oggetto. In particolare, LINQ to DataSet semplifica l'esecuzione di query, consentendo agli sviluppatori di scrivere query dal linguaggio di programmazione stesso, anziché tramite un linguaggio di query separata. Ciò è particolarmente utile per gli sviluppatori di Visual Studio, che possono ora sfruttare i vantaggi del controllo della sintassi in fase di compilazione, tipizzazione statica e supporto IntelliSense resi disponibili da Visual Studio nelle query.  
  
 LINQ to DataSet può anche essere usato per eseguire query su dati che sono stati consolidati da una o più origini dati. In tal modo sono possibili molti scenari in cui è necessario rappresentare e gestire i dati con flessibilità, ad esempio per le query su dati aggregati localmente e la memorizzazione nella cache di livello intermedio nelle applicazioni Web. In particolare, questo tipo di modifiche sono richieste nelle applicazioni generiche per la creazione di rapporti, di analisi e di Business Intelligence.  
  
 LINQ to DataSet funzionalità è esposta principalmente tramite i metodi di estensione nel <xref:System.Data.DataRowExtensions> e <xref:System.Data.DataTableExtensions> classi. LINQ to DataSet si basa su Usa l'architettura ADO.NET esistente e non è destinato a sostituire ADO.NET nel codice dell'applicazione. Il codice ADO.NET esistente continuerà a funzionare in un'applicazione LINQ to DataSet. Nel diagramma seguente viene illustrata la relazione tra LINQ to DataSet ADO.NET e l'archivio dati.  
  
 ![Diagramma che mostra che LINQ to DataSet è basato sul provider ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) - C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ (Language-Integrated Query) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ e ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
