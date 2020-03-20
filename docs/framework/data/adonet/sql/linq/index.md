---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: b0660312f540a69911905edd08541ed70cf39bb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174316"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]è un componente di .NET Framework versione 3.5 che fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti.  
  
> [!NOTE]
> I dati relazionali vengono visualizzati come una raccolta di tabelle bidimensionali (*relazioni* o *file flat*), in cui le colonne comuni collegano tra loro le tabelle. Per usare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in modo efficiente, è necessario avere familiarità con i principi di base dei database relazionali.  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore. Quando viene eseguita l'applicazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che possono essere utilizzati nel linguaggio di programmazione dello sviluppatore.  
  
 Gli sviluppatori che utilizzano Visual Studio utilizzano in genere Object Relational [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Designer, che fornisce un'interfaccia utente per l'implementazione di molte delle funzionalità di .  
  
 Nella documentazione inclusa in questa versione di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono descritti i blocchi di compilazione di base, il processi e le tecniche necessari per la compilazione di applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. È inoltre possibile cercare problemi specifici in Microsoft Docs e partecipare al [forum LINQ](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), in cui è possibile discutere argomenti più complessi in dettaglio con gli esperti. Infine, il white paper [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) descrive in dettaglio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la tecnologia, completa di esempi di codice di Visual Basic e C.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Guida introduttiva](getting-started.md)  
 Viene fornita una panoramica di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e vengono fornite informazioni su come iniziare a usare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Guida alla programmazione](programming-guide.md)  
 Vengono descritte le procedure per eseguire il mapping, creare query, eseguire operazioni di aggiornamento e debug e attività simili.  
  
 [Riferimento](reference.md)  
 Fornisce informazioni di riferimento sui diversi aspetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Tra gli argomenti vengono descritti il mapping dei tipi CLR SQL, la conversione dell'operatore di query standard e altri.  
  
 [Esempi](samples.md)  
 Vengono forniti collegamenti agli esempi di Visual Basic e c.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Query integrata nel linguaggio (LINQ) - CLanguage-Integrated Query (LINQ) - C #](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Vengono fornite una panoramica delle tecnologie LINQ in C.

 [LINQ (Language-Integrated Query) - Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Vengono forniti cenni preliminari sulle tecnologie LINQ in Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Vengono descritte le tecnologie LINQ per gli utenti di Visual Basic.  
  
 [LINQ e ADO.NET](../../linq-and-ado-net.md)  
 Collegamenti al portale di ADO.NET.  
  
 [Procedure dettagliate relative a LINQ to SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Vengono elencate le procedure dettagliate disponibili per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Download di database di esempio](downloading-sample-databases.md)  
 Viene descritto come scaricare i database di esempio usati nella documentazione.  
  
 [Cenni preliminari sul controllo server Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Viene descritto <xref:System.Web.UI.WebControls.LinqDataSource> come il controllo espone Language-Integrated Query (LINQ) agli sviluppatori Web tramite l'architettura del controllo origine dati ASP.NET.
