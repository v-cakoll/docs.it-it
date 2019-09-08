---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 4995512336ee9eb6e33df011757ed533db57e76e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783781"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
LINQ to DataSet semplifica e velocizza l'esecuzione di query sui dati memorizzati nella cache <xref:System.Data.DataSet> in un oggetto. In particolare, LINQ to DataSet semplifica l'esecuzione di query consentendo agli sviluppatori di scrivere query dal linguaggio di programmazione stesso, anziché usando un linguaggio di query distinto. Ciò è particolarmente utile per gli sviluppatori di Visual Studio, che ora possono sfruttare il controllo della sintassi in fase di compilazione, la tipizzazione statica e il supporto IntelliSense fornito da Visual Studio nelle query.  
  
 LINQ to DataSet può essere utilizzato anche per eseguire query su dati che sono stati consolidati da una o più origini dati. In tal modo sono possibili molti scenari in cui è necessario rappresentare e gestire i dati con flessibilità, ad esempio per le query su dati aggregati localmente e la memorizzazione nella cache di livello intermedio nelle applicazioni Web. In particolare, questo tipo di modifiche sono richieste nelle applicazioni generiche per la creazione di rapporti, di analisi e di Business Intelligence.  
  
 La funzionalità LINQ to DataSet viene esposta principalmente tramite i metodi di estensione nelle <xref:System.Data.DataRowExtensions> classi <xref:System.Data.DataTableExtensions> e. LINQ to DataSet si basa su e usa l'architettura ADO.NET esistente e non è destinata a sostituire ADO.NET nel codice dell'applicazione. Il codice ADO.NET esistente continuerà a funzionare in un'applicazione LINQ to DataSet. Il diagramma seguente illustra la relazione tra LINQ to DataSet e ADO.NET e l'archivio dati.  
  
 ![Diagramma che mostra che LINQ to DataSet è basato sul provider ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione](getting-started-linq-to-dataset.md)  
  
 [Guida per programmatori](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) - C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ (Language-Integrated Query) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ e ADO.NET](linq-and-ado-net.md)
- [ADO.NET](index.md)
