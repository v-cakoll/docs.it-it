---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: dce706a9c09558bfb39f0d65bd56b57787488d06
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743268"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è un componente di .NET Framework versione 3.5 che fornisce un'infrastruttura di runtime per la gestione dei dati relazionali come oggetti.  
  
> [!NOTE]
>  I dati relazionali vengono visualizzati come una raccolta di tabelle bidimensionali (*relazioni* o *file flat*), in cui le colonne comuni collegano tra loro le tabelle. Per usare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in modo efficiente, è necessario avere familiarità con i principi di base dei database relazionali.  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando viene eseguita l'applicazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che possono essere utilizzati nel linguaggio di programmazione dello sviluppatore.  
  
 Gli sviluppatori che usano Visual Studio in genere usano Progettazione relazionale oggetti, che fornisce un'interfaccia utente per l'implementazione di molte delle funzionalità di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Nella documentazione inclusa in questa versione di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono descritti i blocchi di compilazione di base, il processi e le tecniche necessari per la compilazione di applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. È possibile anche cercare problemi specifici di Docs Microsoft e per partecipare il [forum su LINQ](https://go.microsoft.com/fwlink/?LinkId=76488)in cui è possibile discutere in dettaglio argomenti più complessi con gli esperti. Infine, il [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper su Dettagli [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tecnologia, con esempi di codice Visual Basic e c#.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Viene fornita una panoramica di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e vengono fornite informazioni su come iniziare a usare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Guida per programmatori](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Vengono descritte le procedure per eseguire il mapping, creare query, eseguire operazioni di aggiornamento e debug e attività simili.  
  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Fornisce informazioni di riferimento sui diversi aspetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Tra gli argomenti vengono descritti il mapping dei tipi CLR SQL, la conversione dell'operatore di query standard e altri.  
  
 [Esempi](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Vengono forniti collegamenti a esempi di Visual Basic e c#.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Language-Integrated Query (LINQ)-C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Viene fornita una panoramica delle tecnologie LINQ in C#.
 
 [LINQ (Language-Integrated Query) - Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Viene fornita una panoramica delle tecnologie LINQ in Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Descrive [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnologie per gli utenti di Visual Basic.  
  
 [LINQ e ADO.NET](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 Collegamenti al portale di ADO.NET.  
  
 [Procedure dettagliate relative a LINQ to SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Vengono elencate le procedure dettagliate disponibili per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Viene descritto come scaricare i database di esempio usati nella documentazione.  
  
 [Cenni preliminari sul controllo Server Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Viene descritto come la <xref:System.Web.UI.WebControls.LinqDataSource> controllo espone [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] agli sviluppatori Web tramite l'architettura del controllo origine dati ASP.NET.
