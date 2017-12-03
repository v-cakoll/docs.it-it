---
title: Glossario di Windows Workflow Foundation per .NET Framework 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Workflow Foundation [WF], glossary
- WF [WF], glossary
ms.assetid: ab682b2f-3779-45ca-b831-b7c03d7dbb3a
caps.latest.revision: "259"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1153b1b87a7b16c330d05a6a89516ab1944bf6e1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="windows-workflow-foundation-glossary-for-net-framework-45"></a>Glossario di Windows Workflow Foundation per .NET Framework 4.5
I termini riportati di seguito sono usati nella documentazione di Windows Workflow Foundation.  
  
## <a name="terms"></a>Termini  
  
|Termine|Definizione|  
|----------|----------------|  
|attività|Unità di comportamento del programma in Windows Workflow Foundation. Le singole attività possono essere riunite in attività più complesse.|  
|azione di attività|Struttura di dati usata per esporre callback per l'esecuzione del flusso di lavoro e dell'attività.|  
|argomento|Definisce il flusso di dati in entrata e in uscita da un'attività. Ogni argomento ha una direzione specificata: in, out o in/out. Rappresentano i parametri di input, output e input/output dell'attività.|  
|segnalibro|Punto nel quale un'attività può essere messa in attesa prima di essere ripresa.|  
|compensazione|Gruppo di azioni progettate per annullare o attenuare l'effetto del lavoro precedentemente completato.|  
|correlazione|Meccanismo per l'instradamento dei messaggi a un'istanza di un flusso di lavoro o di un servizio.|  
|espressione|Costrutto che accetta uno o più argomenti, esegue un'operazione sugli argomenti e restituisce un singolo valore. Le espressioni possono essere usate ovunque possa essere usata un'attività.|  
|diagramma di flusso|Noto paradigma di modellazione che rappresenta i componenti del programma come simboli collegati mediante direzionali.  In .NET Framework 4 è possibile modellare i flussi di lavoro come diagrammi di flusso usando l'attività Diagramma di flusso.|  
|processo a esecuzione prolungata|Unità di esecuzione del programma che non restituisce immediatamente un risultato e può protrarsi per diversi riavvii del sistema.|  
|persistenza|Salvataggio dello stato di un flusso di lavoro o servizio su un supporto durevole, in modo da consentirne lo scaricamento della memoria o il ripristino in seguito a un errore di sistema.|  
|macchina a stati|Noto paradigma di modellazione che rappresenta i componenti del programma come singoli stati collegati mediante transizioni di stato basate su eventi.  I flussi di lavoro possono essere modellati come macchine a stati usando l'attività StateMachine.|  
|sostanza|Rappresenta un gruppo di segnalibri correlati con un identificatore comune e consente al runtime di decidere se la ripresa di un determinato segnalibro è valida o può diventarlo.|  
|convertitore di tipi|Un tipo CLR può essere associato a uno o più tipi derivati di System.ComponentModel.TypeConverter che consentono la conversione di istanze di tipo CLR in e da istanze di altri tipi. Un convertitore di tipi viene associato a un tipo CLR usando l'attributo System.ComponentModel.TypeConverterAttribute.  Un attributo TypeConverterAttribute può essere specificato direttamente nel tipo CLR o in una proprietà. Un convertitore di tipi specificato in una proprietà sarà sempre prioritario rispetto a un convertitore di tipi specificato nel tipo CLR della proprietà.|  
|variabile|Rappresenta l'archiviazione di alcuni dati che devono essere salvati per l'accesso in un momento successivo.|  
|flusso di lavoro|Singola attività o albero di attività richiamate da un processo host.|  
|XAML|eXtensible Application Markup Language|
