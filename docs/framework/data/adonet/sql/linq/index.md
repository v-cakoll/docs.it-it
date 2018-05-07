---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 257db62fcdaba454f528c2eecedfef735291f4af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è un componente di [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] versione 3.5 che fornisce l'infrastruttura di runtime per la gestione di dati relazionali come oggetti.  
  
> [!NOTE]
>  I dati relazionali vengono visualizzati come una raccolta di tabelle bidimensionali (*relazioni* o *file flat*), in cui le colonne comuni collegano tra loro le tabelle. Per usare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in modo efficiente, è necessario avere familiarità con i principi di base dei database relazionali.  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando viene eseguita l'applicazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che possono essere usati nel linguaggio di programmazione dello sviluppatore.  
  
 Gli sviluppatori che usano Visual Studio in genere usare la [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], che fornisce un'interfaccia utente per l'implementazione di molte delle funzionalità di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Nella documentazione inclusa in questa versione di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono descritti i blocchi di compilazione di base, il processi e le tecniche necessari per la compilazione di applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. È inoltre possibile cercare Microsoft Docs problemi specifici e, è possibile partecipare il [forum su LINQ](http://go.microsoft.com/fwlink/?LinkId=76488), in cui è possibile discutere in dettaglio argomenti più complessi con gli esperti. Infine, il [LINQ to SQL: e alle Query per i dati relazionali](http://go.microsoft.com/fwlink/?LinkId=93205) white paper relativo alle dettagli [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la tecnologia di esempi di codice Visual Basic e c#.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Viene fornita una panoramica di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e vengono fornite informazioni su come iniziare a usare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Guida per programmatori](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Vengono descritte le procedure per eseguire il mapping, creare query, eseguire operazioni di aggiornamento e debug e attività simili.  
  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Fornisce informazioni di riferimento sui diversi aspetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Tra gli argomenti vengono descritti il mapping dei tipi CLR SQL, la conversione dell'operatore di query standard e altri.  
  
 [Esempi](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Fornisce collegamenti a esempi di Visual Basic e c#.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 Fornisce una panoramica delle tecnologie [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Viene descritto [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnologie per gli utenti di Visual Basic.  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/library/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 Vengono forniti collegamenti al portale [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)].  
  
 [Procedure dettagliate relative a LINQ to SQL](http://msdn.microsoft.com/library/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 Vengono elencate le procedure dettagliate disponibili per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Viene descritto come scaricare i database di esempio usati nella documentazione.  
  
 [Panoramica della tecnologia LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)  
 Viene descritto come il controllo <xref:System.Web.UI.WebControls.LinqDataSource> consenta di esporre [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] agli sviluppatori Web tramite l'architettura di controllo origine dati di [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)].
