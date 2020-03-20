---
title: Strategia di sicurezza della piattaforma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform security model [WPF]
- Common Language Runtime (CLR) security features
- operating system security model [WPF]
- Internet Explorer security features [WPF]
- Security-Critical method
- CLR security features [WPF]
- security model [WPF]
- security model [WPF], platform
- WPF [WPF], about security model
- Windows Presentation Foundation [WPF], about security model
- security model [WPF], operating system
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
ms.openlocfilehash: 258fcd7c51ea59de03fe60a4eeb9a82dd1c7efca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174602"
---
# <a name="wpf-security-strategy---platform-security"></a>Strategia di sicurezza di WPF - Sicurezza della piattaforma
Mentre Windows Presentation Foundation (WPF) fornisce un'ampia gamma di servizi di sicurezza, sfrutta anche le funzionalità di sicurezza della piattaforma sottostante, che include il sistema operativo, CLR e Internet Explorer. Questi livelli si combinano per fornire WPFWPF un modello di sicurezza forte e di difesa in profondità che tenta di evitare qualsiasi singolo punto di errore, come illustrato nella figura seguente:These layers combine to provide WPFWPF a strong, defense-in-depth security model that attempts to avoid any single point of failure, as shown in the following figure:  
  
 ![Diagramma che mostra il modello di sicurezza WPFWPF.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 Nella parte restante di questo argomento vengono illustrate le funzionalità in ognuno di questi livelli che si occupano di WPFWPF in modo specifico.  

## <a name="operating-system-security"></a>Sicurezza del sistema operativo  
Il nucleo di Windows fornisce diverse funzionalità di sicurezza che costituiscono le basi di sicurezza per tutte le applicazioni Windows, incluse quelle create con WPFWPF. In questo argomento viene illustrata l'ampiezza di queste funzionalità di sicurezza che sono importanti per WPFWPF, nonché come WPFWPF si integra con loro per fornire ulteriore difesa in profondità.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Oltre a una revisione generale e al rafforzamento di Windows, ci sono tre funzionalità chiave di Windows XP SP2 che tratteremo in questo argomento:  
  
- Compilazione /GS  
  
- Microsoft Windows Update.  
  
#### <a name="gs-compilation"></a>Compilazione /GS  
 Windows XP SP2 fornisce protezione ricompilando molte librerie di sistema di base, incluse tutte le dipendenze WPF, ad esempio CLR, per ridurre i sovraccarichi del buffer. A tale scopo, è necessario usare il parametro /GS con il compilatore da riga di comando di C/C++. Anche se i sovraccarichi del buffer dovrebbero essere evitati in modo esplicito, la compilazione /GS rappresenta un esempio di difesa da potenziali vulnerabilità create accidentalmente o intenzionalmente.  
  
 In passato i sovraccarichi del buffer sono stati causa di molte violazioni della sicurezza a impatto elevato. Si verifica un sovraccarico del buffer quando un utente malintenzionato sfrutta una vulnerabilità del codice per introdurre codice dannoso che viene scritto oltre i limiti di un buffer. Il malintenzionato sarà così in grado di assumere il controllo del processo in cui il codice è in esecuzione, sovrascrivendo l'indirizzo di ritorno di una funzione per indurre l'esecuzione del proprio codice dannoso. Il risultato sarà l'esecuzione di codice arbitrario attraverso codice dannoso con gli stessi privilegi del processo di cui è stato assunto il controllo.  
  
 A livello generale, il flag del compilatore -GS protegge da alcuni potenziali sovraccarichi del buffer inserendo un cookie di sicurezza speciale per proteggere l'indirizzo restituito di una funzione con buffer di stringa locale. Dopo la restituzione di un risultato da parte di una funzione, il cookie di sicurezza viene confrontato con il suo valore precedente. Se il valore è cambiato, è possibile che si sia verificato un sovraccarico del buffer e che il processo venga interrotto con una condizione di errore. L'interruzione del processo impedisce l'esecuzione di codice potenzialmente dannoso. Vedere [-GS (controllo](/cpp/build/reference/gs-buffer-security-check) di sicurezza del buffer) per ulteriori dettagli.  
  
 WPFWPF viene compilato con il flag /GS per aggiungere un ulteriore livello di difesa alle applicazioni WPFWPF.  
  
### <a name="windows-vista"></a>Windows Vista  
Gli utenti WPF in Windows Vista trarranno vantaggio dai miglioramenti aggiuntivi della sicurezza del sistema operativo, tra cui "Accesso utente con privilegi minimi", controlli di integrità del codice e isolamento dei privilegi.  
  
#### <a name="user-account-control-uac"></a>Controllo dell'account utente  
 Oggi, gli utenti di Windows tendono a eseguire con privilegi di amministratore perché molte applicazioni li richiedono per l'installazione o l'esecuzione, o entrambi. La scrittura delle impostazioni predefinite di un'applicazione nel Registro di sistema ne è un esempio.  
  
 Usare i privilegi di amministratore per eseguire un'applicazione significa che l'applicazione viene eseguita da processi a cui sono stati concessi i privilegi di amministratore. In termini di sicurezza, ciò significa che eventuale codice dannoso che assume il controllo di un processo eseguito con privilegi di amministratore erediterà automaticamente quei privilegi, incluso l'accesso a risorse di sistema critiche.  
  
 Un modo per proteggersi da una tale minaccia per la sicurezza consiste nell'eseguire le applicazioni con la quantità minima necessaria di privilegi. Questo è noto come il principio dei privilegi minimi ed è una funzionalità fondamentale del sistema operativo Windows. Questa funzionalità è denominata Controllo dell'account utente (UAC) e viene utilizzata dal controllo dell'account utente di Windows in due modi chiave:  
  
- Per eseguire la maggior parte delle applicazioni con privilegi UAC per impostazione predefinita, anche se l'utente è un amministratore. Solo le applicazioni che richiedono i privilegi di amministratore verranno eseguite con i privilegi di amministratore. Per essere eseguite con i privilegi di amministratore, le applicazioni devono essere contrassegnate in modo esplicito nel manifesto dell'applicazione o come voce nei criteri di sicurezza.  
  
- Per fornire soluzioni di compatibilità come la virtualizzazione. Molte applicazioni, ad esempio, provano a scrivere in percorsi limitati, come C:\Programmi. Per le applicazioni eseguite in ambito UAC, esiste un percorso alternativo specifico di ogni utente in cui è possibile scrivere senza disporre dei privilegi di amministratore. Per le applicazioni eseguite in ambito UAC, il percorso C:\Programmi viene virtualizzato affinché le applicazioni scrivano direttamente nel percorso alternativo specifico di ogni utente. Questa soluzione di compatibilità consente di eseguire molte applicazioni che in passato non sarebbe stato possibile eseguire in base al principio UAC.  
  
#### <a name="code-integrity-checks"></a>Controlli di integrità del codice  
 Windows Vista incorpora controlli di integrità del codice più approfonditi per impedire l'iniettatura di codice dannoso nei file di sistema o nel kernel in fase di caricamento/esecuzione. Questo va oltre la protezione dei file di sistema.  

### <a name="limited-rights-process-for-browser-hosted-applications"></a>Processo con diritti limitati per le applicazioni ospitate nei browser  
 Le applicazioni WPF ospitate da browser vengono eseguite all'interno della sandbox dell'area Internet. L'integrazione WPF con Microsoft Internet Explorer estende questa protezione con supporto aggiuntivo.  
  
 Poiché le applicazioni browser XAML (XBAP) sono in genere in modalità sandbox dal set di autorizzazioni dell'area Internet, la rimozione di questi privilegi non danneggia le applicazioni browser XAML (XBAP) dal punto di vista della compatibilità. Viene invece creato un livello di difesa aggiuntivo; se un'applicazione eseguita in una sandbox è in grado di sfruttare altri livelli e di assumere il controllo del processo, il processo disporrà comunque unicamente di privilegi limitati.  
  
 Vedere [Utilizzo di un account utente con privilegi minimi](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
## <a name="common-language-runtime-security"></a>Sicurezza di Common Language Runtime (CLR)  
 Common Language Runtime (CLR) offre una serie di vantaggi chiave per la sicurezza, tra cui la convalida e la verifica, la sicurezza dall'accesso di codice e la metodologia critica per la sicurezza.  

### <a name="validation-and-verification"></a>Convalida e verifica  
 Per fornire l'isolamento e l'integrità degli assembly, CLR utilizza un processo di convalida. La convalida CLR garantisce che gli assembly siano isolati convalidando il formato di file PE (Portable Executable) per gli indirizzi che puntano all'esterno dell'assembly. La convalida CLR convalida inoltre l'integrità dei metadati incorporati in un assembly.  
  
 Per garantire l'indipendenza dai tipi, aiutare a prevenire problemi di sicurezza comuni (ad esempio sovraccarichi del buffer) e abilitare il sandboxing tramite l'isolamento dei sottoprocessi, la sicurezza CLR utilizza il concetto di verifica.  
  
 Le applicazioni gestite vengono compilate in Microsoft Intermediate Language (MSIL). Quando vengono eseguiti metodi in un'applicazione gestita, il relativo MSIL viene compilato in codice nativo tramite la compilazione JIT. La compilazione JIT include un processo di verifica riguardante molte regole di sicurezza e affidabilità per garantire che il codice:  
  
- non violi contratti di tipo  
  
- non causi sovraccarichi del buffer  
  
- non acceda alla memoria in modo irregolare o eccessivo.  
  
 Il codice gestito che non rispetta le regole di verifica non verrà eseguito, a meno che non venga considerato codice attendibile.  
  
 Il vantaggio del codice verificabile è un motivo chiave per cui WPFWPF si basa su .NET Framework. Pertanto, più esteso sarà l'uso di codice verificabile, minori saranno le possibilità di sfruttare le vulnerabilità del sistema.  
  
### <a name="code-access-security"></a>Sicurezza dall'accesso di codice  
 Un computer client espone un'ampia varietà di risorse a cui un'applicazione gestita ha accesso, ad esempio il file system, il Registro di sistema, i servizi di stampa, l'interfaccia utente, la reflection e le variabili di ambiente. Prima che un'applicazione gestita possa accedere a qualsiasi risorsa in un computer client, deve disporre dell'autorizzazione di .NET Framework. Un'autorizzazione in CAS è <xref:System.Security.CodeAccessPermission>una sottoclasse dell'oggetto ; CAS implementa una sottoclasse per ogni risorsa a cui possono accedere le applicazioni gestite.  
  
 Il set di autorizzazioni concesse da un'applicazione gestita da CAS all'avvio dell'esecuzione è noto come set di autorizzazioni ed è determinato dall'evidenza fornita dall'applicazione. Per le applicazioni WPFWPF, l'evidenza fornita è la posizione, o area, da cui vengono avviate le applicazioni. CAS identifica le seguenti zone:  
  
- **Risorse del computer**. Applicazioni avviate dal computer client (completamente attendibili).  
  
- **Intranet locale**. Applicazioni avviate da Intranet (parzialmente attendibili).  
  
- **Internet**. Applicazioni avviate da Internet (meno attendibili).  
  
- **Siti attendibili**. Applicazioni identificate da un utente come attendibili (meno attendibili).  
  
- **Siti non attendibili**. Applicazioni identificate da un utente come non attendibili (non attendibili).  
  
 Per ognuna di queste aree, CAS fornisce un set di autorizzazioni predefinito che include le autorizzazioni che corrisponde al livello di attendibilità associato a ciascuna. incluse le seguenti:  
  
- **FullTrust**. Per le applicazioni avviate dall'area **Risorse del computer.** Sono concesse tutte le autorizzazioni possibili.  
  
- **LocalIntranet**. Per le applicazioni avviate dall'area **Intranet locale.** Viene concesso un sottoinsieme di autorizzazioni per fornire un accesso moderato alle risorse di un computer client, tra cui spazio di memorizzazione isolato, accesso dell'interfaccia utente senza restrizioni, finestre di dialogo di file senza restrizioni, reflection limitata, accesso limitato alle variabili di ambiente. Le autorizzazioni per risorse critiche come il Registro di sistema non vengono concesse.  
  
- **Internet**. Per le applicazioni avviate da **Internet** o dall'area **Siti attendibili.** Viene concesso un sottoinsieme di autorizzazioni per fornire accesso limitato alle risorse di un computer client, tra cui spazio di memorizzazione isolato, solo apertura di file e interfaccia utente limitata. Essenzialmente, questo set di autorizzazioni isola le applicazioni dal computer client.  
  
 Alle applicazioni identificate come provenienti dall'area **Siti non attendibili** non vengono concesse autorizzazioni da CAS. Di conseguenza, queste non dispongono di alcun set di autorizzazioni predefinito.  
  
 Nella figura seguente viene illustrata la relazione tra aree, set di autorizzazioni, autorizzazioni e risorse:  
  
 ![Diagramma che mostra i set di autorizzazioni CAS.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Le restrizioni della sandbox di sicurezza dell'area Internet si applicano ugualmente a qualsiasi codice importato da un'applicazione XBAP da una libreria di sistema, incluso WPF. Ciò garantisce che ogni bit del codice viene bloccato, anche WPFWPF. Sfortunatamente, per poter essere eseguito, un'applicazione XBAP deve eseguire funzionalità che richiedono più autorizzazioni rispetto a quelle abilitate dalla sandbox di sicurezza dell'area Internet.  
  
 Si consideri un'applicazione XBAP che include la pagina seguente:Consider an XBAP application that includes the following page:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Per eseguire questo 'XBAP, il codice WPF sottostante deve eseguire più funzionalità di quelle disponibili per la chiamata XBAP, tra cui:  
  
- Creazione di un handle di finestra (HWND) per il renderingCreating a window handle (HWND) for rendering  
  
- Invio di messaggi  
  
- Caricamento del tipo di carattere Tahoma  
  
 Da un punto di vista della sicurezza, consentire l'accesso diretto a queste operazioni dall'applicazione eseguita in una sandbox avrebbe conseguenze devastanti.  
  
 Fortunatamente, WPFWPF soddisfa questa situazione consentendo l'esecuzione di queste operazioni con privilegi elevati per conto dell'applicazione in modalità sandbox. Mentre tutte le operazioni WPFWPF vengono confrontate con le autorizzazioni di sicurezza dell'area Internet limitate del dominio applicazione di XBAP, WPFWPF (come con altre librerie di sistema) viene concesso un set di autorizzazioni che include tutte le autorizzazioni possibili.
  
 Ciò richiede che WPFWPF riceva privilegi elevati impedendo che tali privilegi vengano gestiti dal set di autorizzazioni dell'area Internet del dominio applicazione host.  
  
 WPFWPF esegue questa operazione utilizzando il **metodo Assert** di un'autorizzazione. Nel codice riportato di seguito viene illustrata questa operazione.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 **L'assert** impedisce essenzialmente che le autorizzazioni illimitate richieste da WPF vengano limitate dalle autorizzazioni dell'area Internet di XBAP.  
  
 Dal punto di vista della piattaforma, WPFWPF è responsabile dell'utilizzo corretto di **Assert;** un uso non corretto di **Assert** potrebbe consentire al codice dannoso di elevare i privilegi. Di conseguenza, è importante chiamare **Assert** solo quando necessario e garantire che le restrizioni della sandbox rimangano intatte. Ad esempio, al codice sandbox non è consentita l'apertura di file casuali, ma è consentito l'uso dei tipi di carattere. WPFWPF consente alle applicazioni in modalità sandbox di utilizzare la funzionalità dei tipi di carattere chiamando **Assert**e per WPFWPF di leggere i file noti per contenere tali tipi di carattere per conto dell'applicazione in modalità sandbox.  
  
### <a name="clickonce-deployment"></a>Distribuzione ClickOnce  
 ClickOnce è una tecnologia di distribuzione completa inclusa in .NET Framework e si integra con Visual Studio (per informazioni dettagliate sulla sicurezza e sulla [distribuzione ClickOnce).](/visualstudio/deployment/clickonce-security-and-deployment) Le applicazioni WPF autonome possono essere distribuite tramite ClickOnce, mentre le applicazioni ospitate da browser devono essere distribuite con ClickOnce.Standalone WPF applications can be deployed using ClickOnceClickOnce, while browser-hosted applications must be deployed with ClickOnceClickOnce.  
  
 Alle applicazioni distribuite tramite ClickOnceClickOnce viene assegnato un livello di sicurezza aggiuntivo rispetto alla sicurezza dall'accesso di codice. essenzialmente, clickOnceClickOnce applicazioni distribuite richiedono le autorizzazioni necessarie. A tali applicazioni vengono concesse solo quelle autorizzazioni se non superano l'insieme di autorizzazioni dell'area da cui vengono distribuite. Riducendo il set di autorizzazioni solo a quelle necessarie, anche se sono inferiori a quelle fornite dal set di autorizzazioni dell'area di avvio, il numero di risorse a cui l'applicazione ha accesso viene ridotto al minimo. Di conseguenza, se si perde il controllo dell'applicazione, le vulnerabilità del computer client saranno ridotte.  
  
### <a name="security-critical-methodology"></a>Metodologia critica per la sicurezza  
 Il codice WPFWPF che usa le autorizzazioni per abilitare la sandbox dell'area Internet per le applicazioni XBAP deve essere mantenuto al massimo livello possibile di controllo e controllo della sicurezza. Per facilitare questo requisito, .NET Framework fornisce un nuovo supporto per la gestione del codice che eleva i privilegi. In particolare, CLR consente di identificare il codice che <xref:System.Security.SecurityCriticalAttribute>eleva i privilegi e contrassegnarlo con l'oggetto ; qualsiasi codice non <xref:System.Security.SecurityCriticalAttribute> contrassegnato con diventa *trasparente* utilizzando questa metodologia. Viceversa, il codice gestito non contrassegnato con <xref:System.Security.SecurityCriticalAttribute> non può elevare i privilegi.  
  
 La metodologia Security-Critical consente all'organizzazione di codice WPF che eleva i privilegi in kernel critici per la *sicurezza,* mentre il resto è trasparente. L'isolamento del codice critico per la sicurezza consente al team di progettazione WPF concentrarsi su un'ulteriore analisi della sicurezza e controllo del codice sorgente sulle procedure di sicurezza standard del kernel critico per la sicurezza (vedere [Strategia](wpf-security-strategy-security-engineering.md)di sicurezza WPF - Security Engineering ).  
  
 Si noti che .NET Framework consente al codice attendibile di estendere la sandbox <xref:System.Security.AllowPartiallyTrustedCallersAttribute> dell'area Internet XBAP consentendo agli sviluppatori di scrivere assembly gestiti contrassegnati con (APTCA) e distribuiti nella Global Assembly Cache (GAC) dell'utente. Contrassegnare un assembly con APTCA è un'operazione estremamente delicata dal punto di vista della sicurezza in quanto consente a qualsiasi codice di chiamare quell'assembly, incluso eventuale codice dannoso proveniente da Internet. È necessario esercitare massima cautela, seguire le procedure consigliate e gli utenti devono scegliere di considerare attendibile un programma software per poterlo installare.  
  
## <a name="microsoft-internet-explorer-security"></a>Sicurezza di Microsoft Internet Explorer  
 Oltre a ridurre i problemi di sicurezza e semplificare la configurazione della sicurezza, Microsoft Internet Explorer 6 (SP2) contiene diverse funzionalità che migliorano la sicurezza che migliorano la sicurezza per gli utenti di applicazioni browser XAML (XBAP). Tramite queste funzionalità si tenta di fornire agli utenti un maggiore controllo sulla loro esperienza di esplorazione.  
  
 Prima di IE6 SP2, gli utenti potevano essere soggetti a uno dei seguenti elementi:  
  
- Finestre popup casuali.  
  
- Reindirizzamento di script non chiaro.  
  
- Numerose finestre di dialogo di sicurezza in alcuni siti Web.  
  
 In alcuni casi, siti Web inaffidabili tentano di ingannare gli utenti eseguendo lo spoofing dell'installazione [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] o visualizzando ripetutamente una finestra di dialogo di installazione di Microsoft ActiveX, anche se l'utente potrebbe averlo annullato. Tramite queste tecniche, è possibile che un numero significativo di utenti sia stato indotto a prendere decisioni che hanno causato l'installazione di applicazioni spyware.  
  
 IE6 SP2 include diverse funzionalità per attenuare questi tipi di problemi, che ruotano intorno al concetto di avvio dell'utente. IE6 SP2 rileva quando un utente ha fatto clic su un collegamento o un elemento di pagina prima di un'azione, noto come *avvio dell'utente,* e lo considera in modo diverso rispetto a quando un'azione simile viene invece attivata dallo script in una pagina. Ad esempio, IE6 SP2 incorpora un **blocco popup** che rileva quando un utente fa clic su un pulsante prima della creazione di un popup. Ciò consente a IE6 SP2 di consentire la maggior parte dei popup innocui, impedendo al contempo i popup che gli utenti non chiedono né desiderano. I popup bloccati sono intrappolati sotto la nuova **barra delle informazioni**, che consente all'utente di sostituire manualmente il blocco e visualizzare il popup.  
  
 La stessa logica di avvio dell'utente viene applicata anche ai prompt di sicurezza **apri**/**salvataggio.** Le finestre di dialogo di installazione ActiveX sono sempre intrappolate sotto la barra delle informazioni, a meno che non rappresentino un aggiornamento da un controllo installato in precedenza. Queste misure consentono agli utenti un'esperienza più controllata e sicura, perché sono protetti da quei siti che con l'inganno inducono a installare software indesiderato o dannoso.  
  
 Queste funzionalità proteggono anche i clienti che utilizzano IE6 SP2 per passare a i siti Web che consentono loro di scaricare e installare applicazioni WPF. In particolare, ciò è dovuto al fatto che IE6 SP2 offre un'esperienza utente migliore che riduce la possibilità per gli utenti di installare applicazioni dannose o subdole indipendentemente dalla tecnologia utilizzata per compilarla, incluso WPFWPF. WPFWPF aggiunge a queste protezioni utilizzando ClickOnce per facilitare il download delle applicazioni su Internet. Poiché le applicazioni browser XAML (XBAP) vengono eseguite all'interno di una sandbox di sicurezza dell'area Internet, possono essere avviate senza problemi. D'altra parte, le applicazioni WPF autonome richiedono l'attendibilità totale per l'esecuzione. Per queste applicazioni, ClickOnceClickOnce visualizzerà una finestra di dialogo di sicurezza durante il processo di avvio per notificare l'utilizzo dei requisiti di sicurezza aggiuntivi dell'applicazione. Questa operazione, che deve essere avviata dall'utente, verrà determinata dalla logica avviata dall'utente e potrà essere annullata.  
  
 Internet Explorer 7 incorpora ed estende le funzionalità di sicurezza di Internet Explorer 2 come parte di un impegno costante per la sicurezza.  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza dall'accesso di codiceCode Access Security](../misc/code-access-security.md)
- [Sicurezza](security-wpf.md)
- [Sicurezza dell'attendibilità parziale WPFWPF Partial Trust Security](wpf-partial-trust-security.md)
- [Strategia di sicurezza WPF - Progettazione della sicurezza](wpf-security-strategy-security-engineering.md)
