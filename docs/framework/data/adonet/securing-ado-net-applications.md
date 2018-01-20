---
title: Protezione delle applicazioni ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 75d78c505c81ce688e0ba0110c76712c71db1c4f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="securing-adonet-applications"></a>Protezione delle applicazioni ADO.NET
Per scrivere un'applicazione ADO.NET protetta, non è sufficiente evitare i problemi più comuni di codifica, ad esempio la mancata convalida dell'input dell'utente. Un'applicazione che consente di accedere ai dati può presentare molti punti di errore, che possono essere sfruttati da utenti non autorizzati per recuperare, modificare o distruggere dati sensibili. È pertanto importante considerare tutti gli aspetti della sicurezza, a partire dal processo di classificazione dei rischi durante la fase di progettazione dell'applicazione, fino all'eventuale distribuzione e alla manutenzione costante.  
  
 Con .NET Framework vengono forniti numerosi servizi, classi e strumenti utili per la protezione e l'amministrazione di applicazioni di database. Common Language Runtime (CLR) fornisce un ambiente indipendente dai tipi in cui eseguire il codice, con una Sicurezza dall'accesso di codice (CAS, Code Access Security) per limitare ulteriormente le autorizzazioni del codice gestito. Attenendosi alle tecniche per la generazione di codice di accesso ai dati protetto, è possibile limitare i danni inflitti da un potenziale utente non autorizzato.  
  
 Il codice protetto non difende dai problemi di sicurezza che si possono verificare quando si usano risorse non gestite quali i database. La maggior parte dei database di server, ad esempio SQL Server, dispone di sistemi di sicurezza interni, che aumentano la protezione se correttamente implementati. Tuttavia, anche un'origine dati con un sistema di sicurezza efficace può subire danni da un attacco se non è configurata in modo appropriato.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica della sicurezza](../../../../docs/framework/data/adonet/security-overview.md)  
 Vengono forniti consigli per la progettazione di applicazioni ADO.NET protette.  
  
 [Accesso sicuro ai dati](../../../../docs/framework/data/adonet/secure-data-access.md)  
 Viene descritto come usare i dati di un'origine dati protetta.  
  
 [Applicazioni client sicure](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 Vengono riportate alcune considerazioni sulla sicurezza per le applicazioni client.  
  
 [Sicurezza dell'accesso di codice e ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)  
 Viene descritto come usare la sicurezza dall'accesso di codice per migliorare la protezione del codice ADO.NET. Viene inoltre illustrato come operare in un contesto di attendibilità parziale.  
  
 [Privacy e sicurezza dei dati](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 Vengono descritte le opzioni di crittografia disponibili per le applicazioni ADO.NET.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sicurezza di SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 Vengono descritte le funzionalità di sicurezza di SQL Server dal punto di vista di uno sviluppatore.  
  
 [Considerazioni sulla sicurezza](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 Viene descritta la sicurezza per le applicazioni Entity Framework.  
  
 [Sicurezza](../../../../docs/standard/security/index.md)  
 Contiene collegamenti ad argomenti in cui vengono descritti tutti gli aspetti della sicurezza in .NET Framework.  
  
 [Strumenti di sicurezza](http://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 Vengono fornite informazioni sugli strumenti di .NET Framework per la protezione e l'amministrazione dei criteri di sicurezza.  
  
 [Risorse per la creazione di applicazioni sicure](http://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 Vengono forniti collegamenti ad argomenti relativi alla creazione di applicazioni protette.  
  
 [Bibliografia sulla sicurezza](/visualstudio/ide/security-bibliography)  
 Vengono forniti collegamenti a risorse esterne disponibili online e in formato cartaceo.  
  
## <a name="see-also"></a>Vedere anche  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
