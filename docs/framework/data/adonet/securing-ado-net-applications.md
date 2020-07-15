---
title: Protezione delle applicazioni
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 1e08bb2386dff5d824d46aba652609ec5a373008
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374520"
---
# <a name="securing-adonet-applications"></a>Protezione delle applicazioni ADO.NET

Per scrivere un'applicazione ADO.NET protetta, non è sufficiente evitare i problemi più comuni di codifica, ad esempio la mancata convalida dell'input dell'utente. Un'applicazione che accede ai dati presenta numerosi punti di errore potenziali che un pirata informatico può sfruttare recuperare, modificare o distruggere dati sensibili. È pertanto importante considerare tutti gli aspetti della sicurezza, a partire dal processo di classificazione dei rischi durante la fase di progettazione dell'applicazione, fino all'eventuale distribuzione e alla manutenzione costante.  
  
Con .NET Framework vengono forniti numerosi servizi, classi e strumenti utili per la protezione e l'amministrazione di applicazioni di database. Common Language Runtime (CLR) fornisce un ambiente indipendente dai tipi in cui eseguire il codice, con una Sicurezza dall'accesso di codice (CAS, Code Access Security) per limitare ulteriormente le autorizzazioni del codice gestito. Attenendosi alle tecniche per la generazione di codice di accesso ai dati protetto, è possibile limitare i danni inflitti da un potenziale utente non autorizzato.  
  
Il codice protetto non difende dai problemi di sicurezza che si possono verificare quando si usano risorse non gestite quali i database. La maggior parte dei database di server, ad esempio SQL Server, dispone di sistemi di sicurezza interni, che aumentano la protezione se correttamente implementati. Tuttavia, anche un'origine dati con un sistema di sicurezza efficace può subire danni da un attacco se non è configurata in modo appropriato.  
  
## <a name="in-this-section"></a>Contenuto della sezione

 [Panoramica della sicurezza](security-overview.md)  
 Vengono forniti consigli per la progettazione di applicazioni ADO.NET protette.  
  
 [Accesso sicuro ai dati](secure-data-access.md)  
 Viene descritto come usare i dati di un'origine dati protetta.  
  
 [Applicazioni client sicure](secure-client-applications.md)  
 Vengono riportate alcune considerazioni sulla sicurezza per le applicazioni client.  
  
 [Sicurezza dell'accesso di codice e ADO.NET](code-access-security.md)  
 Viene descritto come usare la sicurezza dall'accesso di codice per migliorare la protezione del codice ADO.NET. Viene inoltre illustrato come operare in un contesto di attendibilità parziale.  
  
 [Privacy e sicurezza dei dati](privacy-and-data-security.md)  
 Vengono descritte le opzioni di crittografia disponibili per le applicazioni ADO.NET.  
  
## <a name="related-sections"></a>Sezioni correlate

 [Linee guida sulla sicurezza di DataSet e DataTable](dataset-datatable-dataview/security-guidance.md)  
 Fornisce indicazioni sulla sicurezza per <xref:System.Data.DataSet> e <xref:System.Data.DataTable> .

 [Sicurezza SQL Server](./sql/sql-server-security.md)  
 Vengono descritte le funzionalità di sicurezza di SQL Server dal punto di vista di uno sviluppatore.  
  
 [Security Considerations](./ef/security-considerations.md)  
 Viene descritta la sicurezza per le applicazioni Entity Framework.  
  
 [Sicurezza](../../../standard/security/index.md)  
 Contiene collegamenti ad articoli che descrivono tutti gli aspetti della sicurezza in .NET.  
  
 [Strumenti di sicurezza](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))  
 Vengono fornite informazioni sugli strumenti di .NET Framework per la protezione e l'amministrazione dei criteri di sicurezza.  
  
 [Risorse per la creazione di applicazioni sicure](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))  
 Fornisce collegamenti ad articoli per la creazione di applicazioni protette.  
  
 [Bibliografia sulla sicurezza](/visualstudio/ide/securing-applications)  
 Vengono forniti collegamenti a risorse esterne disponibili online e in formato cartaceo.  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET](index.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
