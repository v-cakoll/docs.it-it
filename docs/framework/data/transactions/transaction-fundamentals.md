---
title: Nozioni fondamentali sulle transazioni
description: Esaminare le nozioni fondamentali sulle transazioni in .NET. Tutte le transazioni devono possedere le proprietà ACID di base (atomicità, coerenza, isolamento e durabilità).
ms.date: 03/30/2017
ms.assetid: 353f4ee2-e6bf-4b1c-b1c8-385fc8a486c0
ms.openlocfilehash: 49292172b07985d379bfa5d520798d7d97af5749
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141939"
---
# <a name="transaction-fundamentals"></a>Nozioni fondamentali sulle transazioni
Le transazioni consentono di associare più attività fra loro. Ad esempio, si supponga che un'applicazione esegua due attività. La prima consiste nel creare una nuova tabella in un database. La seconda consiste nel chiamare un oggetto specifico per raccogliere, formattare e inserire dati nella nuova tabella. Queste due attività sono correlate e persino interdipendenti, nel senso che la creazione di una tabella deve avvenire esclusivamente quando sono disponibili dei dati con cui riempirla. L'esecuzione di entrambe le attività nell'ambito di un'unica transazione ne garantisce la correlazione. Se si verifica un errore nella seconda attività, il sistema esegue il rollback della prima attività a un punto precedente alla creazione della nuova tabella.  
  
 Affinché presentino un comportamento prevedibile, tutte le transazioni devono possedere le proprietà ACID, ovvero atomicità, coerenza, isolamento e durata. Queste proprietà garantiscono il ruolo delle transazioni di importanza critica come proposte di coerenza completa. Per ulteriori informazioni su ACID, vedere [proprietà ACID](/windows/win32/cossdk/acid-properties). In breve, le proprietà ACID garantiscono che più attività correlate abbiano tutte lo stesso esito, sia esso negativo o positivo. Ovvero, nella terminologia dell'elaborazione delle transazioni, la transazione viene interrotta o ne viene eseguito il commit. Affinché venga eseguito il commit di una transazione, tutte le attività componenti devono garantire che qualsiasi modifica ai dati sia definitiva. Le modifiche devono essere definitive anche in caso di arresti anomali del sistema o altri eventi imprevisti. Se anche una sola delle attività componenti non è in grado di fornire questa garanzia, l'intera transazione ha esito negativo. In tal caso, per tutte le modifiche apportate ai dati nell'ambito della transazione viene eseguito il rollback a un punto impostato specifico.  
  
 Una transazione può riguardare esclusivamente un'unica risorsa di dati, ad esempio un database o una coda di messaggi. In questo scenario la transazione locale viene gestita dalla gestione transazioni fornita dallo spazio dei nomi <xref:System.Transactions> che comporta un miglioramento delle prestazioni. Queste transazioni, controllate dalla risorsa di dati, sono efficienti e facili da gestire.  
  
 Le transazioni possono riguardare anche più risorse di dati. Le transazioni distribuite consentono di incorporare varie operazioni distinte in esecuzione su più sistemi in un'unica azione con esito positivo o negativo. In questo scenario, le transazioni vengono coordinate dallo strumento MSDTC (Microsoft Distributed Transaction Coordinator) presente in ogni sistema.  
  
 Quando si sviluppa un'applicazione transazionale utilizzando le classi fornite dallo spazio dei nomi <xref:System.Transactions> non è necessario gestire manualmente i tipi di transazione da utilizzare o determinare la gestione transazioni coinvolta, in quanto queste problematiche vengono gestite automaticamente dall'infrastruttura <xref:System.Transactions>.  
  
 Quando si crea una transazione è possibile specificarne il livello di isolamento. Il livello di isolamento, definito dall' <xref:System.Transactions.IsolationLevel> enumerazione, determina il livello di accesso che altre transazioni avranno sui dati interessati dalla transazione.  
  
 È possibile creare transazioni utilizzando ADO.NET, <xref:System.EnterpriseServices> o il modello di programmazione transazionale fornito dallo <xref:System.Transactions> spazio dei nomi. Nell'argomento [funzionalità fornite da System. Transactions](features-provided-by-system-transactions.md) vengono illustrate le funzionalità che è possibile utilizzare per scrivere un'applicazione transazionale utilizzando lo <xref:System.Transactions> spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità offerte da System.Transactions](features-provided-by-system-transactions.md)
