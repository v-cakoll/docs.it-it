---
title: Applicazioni client sicure
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: a3b035d59a39ca20f6a81fbd40d39069a7cc43c2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208556"
---
# <a name="secure-client-applications"></a>Applicazioni client sicure
Le applicazioni sono costituite in genere da molte parti che è necessario proteggere da vulnerabilità che potrebbero causare la perdita di dati o compromettere in altro modo il sistema. La creazione di interfacce utente protette consente di impedire molti problemi bloccando gli utenti non autorizzati prima che accedano ai dati o alle risorse del sistema.  
  
## <a name="validate-user-input"></a>Convalidare l'input dell'utente  
 Quando si crea un'applicazione che accede a dati, è opportuno presupporre che tutto l'input dell'utente sia dannoso fino a prova contraria. In caso contrario, si espone l'applicazione a potenziali attacchi. In .NET Framework sono incluse classi che consentono di applicare un dominio di valori per i controlli di input, ad esempio limitando il numero di caratteri che è possibile immettere. Gli hook di evento consentono di scrivere procedure per verificare la validità dei valori. I dati dell'input dell'utente possono essere convalidati e fortemente tipizzati, limitando l'esposizione di un'applicazione ad attacchi tramite script e di tipo SQL injection.  
  
> [!IMPORTANT]
>  È inoltre necessario convalidare l'input dell'utente nell'origine dati nonché nell'applicazione dati. Un utente non autorizzato può scegliere di aggirare l'applicazione e attaccare direttamente l'origine dati.  
  
 [Sicurezza e input dell'utente](../../../../docs/standard/security/security-and-user-input.md)  
 Viene descritto come gestire i bug di difficile individuazione e potenzialmente pericolosi che riguardano l'input dell'utente.  
  
 [Convalida dell'Input utente nelle pagine Web ASP.NET](https://msdn.microsoft.com/library/4ad3dacb-89e0-4cee-89ac-40a3f2a85461)  
 Viene fornita una panoramica della convalida dell'input dell'utente tramite gli appositi controlli di ASP.NET.  
  
 [Input dell'utente in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 Vengono forniti collegamenti e informazioni per la convalida dell'input da mouse e tastiera in un'applicazione Windows Forms.  
  
 [Espressioni regolari di .NET Framework](../../../../docs/standard/base-types/regular-expressions.md)  
 Viene descritto come usare la classe <xref:System.Text.RegularExpressions.Regex> per verificare la validità dell'input dell'utente.  
  
## <a name="windows-applications"></a>Applicazioni Windows  
 In passato, le applicazioni Windows venivano in genere eseguite con autorizzazioni complete. Con .NET Framework viene fornita l'infrastruttura necessaria per limitare l'esecuzione di codice in un'applicazione Windows tramite la sicurezza dall'accesso di codice. Questa funzionalità non è tuttavia sufficiente, da sola, a proteggere l'applicazione.  
  
 [Sicurezza di Windows Form](../../../../docs/framework/winforms/windows-forms-security.md)  
 Viene illustrato come proteggere le applicazioni Windows Forms e vengono forniti collegamenti ad argomenti correlati.  
  
 [Windows Form e applicazioni non gestite](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 Viene descritto come interagire con applicazioni non gestite in un'applicazione Windows Forms.  
  
 [Distribuzione ClickOnce per Windows Forms Application](https://msdn.microsoft.com/library/34d8c770-48f2-460c-8d67-4ea5684511df)  
 Viene descritto come usare la distribuzione `ClickOnce` in un'applicazione Windows Form e ne vengono illustrate le implicazioni per la sicurezza.  
  
## <a name="aspnet-and-xml-web-services"></a>Servizi Web ASP.NET e XML  
 In genere, nelle applicazioni ASP.NET è necessario limitare l'accesso ad alcune parti del sito Web e fornire meccanismi diversi per la protezione dei dati e la sicurezza del sito. Questi collegamenti forniscono informazioni utili per la protezione dell'applicazione ASP.NET.  
  
 Un servizio Web XML fornisce dati che possono essere usati da un'applicazione ASP.NET, un'applicazione Windows Form o un altro servizio Web. È necessario gestire la sicurezza per il servizio Web stesso così come quella per l'applicazione client.  
  
 Per altre informazioni, vedere le seguenti risorse.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[NIB: Protezione ASP.NET](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d)|Viene illustrato come proteggere le applicazioni ASP.NET.|  
|[Protezione dei servizi Web XML creati tramite ASP.NET](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c)|Viene illustrato come implementare la sicurezza per un servizio Web ASP.NET.|  
|[Panoramica di attacchi tramite script](https://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|Viene descritto come salvaguardarsi da attacchi tramite script, in cui si tenta di inserire caratteri dannosi in una pagina Web.|  
|[NIB: base procedure consigliate per le applicazioni Web ASP.NET](https://msdn.microsoft.com/library/94a52ab8-731d-417e-b997-721baf43df38)|Informazioni generali sulla sicurezza e collegamenti ad ulteriori argomenti.|  
  
## <a name="remoting"></a>Servizi remoti  
 Con .NET Remoting è possibile compilare facilmente applicazioni ampiamente distribuite, sia che i componenti dell'applicazione si trovino tutti nello stesso computer o dislocati in varie parti del mondo. È possibile compilare applicazioni client che usano oggetti di altri processi nello stesso computer o in qualsiasi altro computer disponibile sulla rete. È anche possibile usare .NET Remoting per comunicare con altri domini applicazione nello stesso processo.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Configurazione di applicazioni Remote](https://msdn.microsoft.com/library/92c0c097-d984-4315-835b-7490ecdf1097)|Viene descritto come configurare le applicazioni remote per evitare problemi comuni.|  
|[Sicurezza in .NET Remoting](https://msdn.microsoft.com/library/9574262c-d4b1-41c5-8600-24ff147c0add)|Vengono descritte l'autenticazione e la crittografia e sono riportati altri argomenti sulla sicurezza relativi ai servizi remoti.|  
|[Considerazioni sulla sicurezza e la comunicazione remota](../../../../docs/framework/misc/security-and-remoting-considerations.md)|Vengono descritti i problemi di sicurezza con gli oggetti protetti e l'uso di più domini di applicazioni.|  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Raccomandazioni per strategie di accesso ai dati](https://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [Protezione delle applicazioni](/visualstudio/ide/securing-applications)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
