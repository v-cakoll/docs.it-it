---
title: Protezione delle informazioni di connessione
description: Informazioni sulle vulnerabilità di sicurezza nelle stringhe di connessione, che possono verificarsi a causa del modo in cui le stringhe di connessione vengono costruite e rese permanente e il tipo di autenticazione.
ms.date: 03/30/2017
ms.assetid: 1471f580-bcd4-4046-bdaf-d2541ecda2f4
ms.openlocfilehash: 0e693fd99384a2808a621b358f8e70c6777c3930
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286650"
---
# <a name="protecting-connection-information"></a>Protezione delle informazioni di connessione
La protezione dell'accesso all'origine dati è uno dei principali obiettivi da raggiungere quando si imposta la sicurezza di un'applicazione. Una stringa di connessione presenta una potenziale vulnerabilità se non è protetta. Se le informazioni di connessione vengono archiviate in testo normale o mantenute nella memoria, si rischia di compromettere l'intero sistema. Le stringhe di connessione incorporate nel codice sorgente possono essere lette usando [Ildasm. exe (DISASSEMBLER il)](../../tools/ildasm-exe-il-disassembler.md) per visualizzare Microsoft Intermediate Language (MSIL) in un assembly compilato.  
  
 Le vulnerabilità di sicurezza che riguardano le stringhe di connessione possono presentarsi in base al tipo di autenticazione usato, alla modalità con cui le stringhe di connessione vengono mantenute nella memoria e su disco e alle tecniche usate per crearle in fase di esecuzione.  
  
## <a name="use-windows-authentication"></a>Usa autenticazione di Windows  
 Per limitare l'accesso all'origine dati, è necessario proteggere le informazioni di connessione quali, ad esempio, identificatore utente, password e nome dell'origine dati. Per evitare di esporre le informazioni sugli utenti, è consigliabile usare l'autenticazione di Windows (talvolta definita *sicurezza integrata*) laddove possibile. L'autenticazione di Windows viene specificata in una stringa di connessione usando le parole chiave `Integrated Security` o `Trusted_Connection`, eliminando la necessità di usare un ID utente e una password. Tramite l'autenticazione di Windows, gli utenti vengono autenticati da Windows e l'accesso alle risorse di server e database viene determinato concedendo autorizzazioni a utenti e gruppi di Windows.  
  
 Nei casi in cui non sia possibile usare l'autenticazione di Windows, è necessario prestare una maggiore attenzione perché le credenziali utente sono esposte nella stringa di connessione. Nelle applicazioni ASP.NET è possibile configurare un account di Windows come identità fissa usata per le connessioni a database e ad altre risorse di rete. È possibile abilitare la rappresentazione nell'elemento Identity nel file **Web. config** e specificare un nome utente e una password.  
  
```xml  
<identity impersonate="true"
        userName="MyDomain\UserAccount"
        password="*****" />  
```  
  
 L'account con identità fissa deve avere privilegi limitati che includono solo le autorizzazioni necessarie nel database. È inoltre necessario crittografare il file di configurazione in modo da non esporre il nome utente e la password in testo non crittografato.  
  
## <a name="do-not-use-universal-data-link-udl-files"></a>Non usare file UDL (Universal Data Link)  
 Evitare di archiviare le stringhe di connessione per <xref:System.Data.OleDb.OleDbConnection> in un file di collegamento dati universale (UDL). I file UDL vengono archiviati in testo non crittografato e non possono essere crittografati. Poiché per l'applicazione si tratta di una risorsa esterna basata su file, un file UDL non può essere protetto né crittografato tramite .NET Framework.  
  
## <a name="avoid-injection-attacks-with-connection-string-builders"></a>Evitare attacchi injection con i compilatori di stringhe di connessione  
 Un attacco injection alle stringhe di connessione può verificarsi quando si usa la concatenazione dinamica di stringhe per compilare stringhe di connessione basate sull'input dell'utente. Se l'input dell'utente non viene convalidato e il testo o i caratteri dannosi non vengono convertiti in caratteri di escape, un utente non autorizzato potrebbe accedere a dati sensibili o ad altre risorse del server. Per risolvere questo problema, in ADO.NET 2.0 sono state introdotte nuove classi di compilatori di stringhe di connessione per convalidare la sintassi delle stringhe e assicurarsi che non vengano inseriti parametri aggiuntivi. Per altre informazioni, vedere [Compilatori di stringhe di connessione](connection-string-builders.md).  
  
## <a name="use-persist-security-infofalse"></a>Usare Persist Security Info=False  
 Il valore predefinito per `Persist Security Info` è false; si consiglia di usare questo valore in tutte le stringhe di connessione. Se si imposta `Persist Security Info` su `true` o `yes`, è possibile che da una connessione aperta si ottengano informazioni sensibili, tra cui l'ID utente e la password. Se si imposta `Persist Security Info` su `false` o `no`, le informazioni di sicurezza vengono eliminate dopo essere state usate per aprire la connessione. In questo modo un'origine non attendibile non ha accesso alle informazioni sensibili per la sicurezza.  
  
## <a name="encrypt-configuration-files"></a>Crittografare i file di configurazione  
 È anche possibile archiviare le stringhe di connessione in file di configurazione, eliminando la necessità di incorporarle nel codice dell'applicazione. I file di configurazione sono file XML standard per i quali in .NET Framework è stato definito un set comune di elementi. Le stringhe di connessione nei file di configurazione vengono in genere archiviate all'interno dell' **\<connectionStrings>** elemento nel file **app. config** per un'applicazione Windows o nel file **Web. config** per un'applicazione ASP.NET. Per ulteriori informazioni sulle nozioni di base per l'archiviazione, il recupero e la crittografia delle stringhe di connessione dai file di configurazione, vedere [stringhe di connessione e file di configurazione](connection-strings-and-configuration-files.md).  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](securing-ado-net-applications.md)
- [Crittografia delle informazioni di configurazione tramite la configurazione protetta](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))
- [Sicurezza in .NET](../../../standard/security/index.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
