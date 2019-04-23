---
title: 'Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro'
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86fc35ae20211bd32a21d60b7313074361aef671
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296173"
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a>Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro
A partire da .NET Framework versione 3.5 Service Pack 1 (SP1), le firme con nome sicuro non vengono convalidate quando un assembly viene caricato in un oggetto <xref:System.AppDomain> con attendibilità totale, ad esempio l'oggetto predefinito <xref:System.AppDomain> per la zona `MyComputer`. Questo comportamento è reso possibile dalla funzionalità che consente di ignorare la verifica del nome sicuro. In un ambiente ad attendibilità totale le richieste di <xref:System.Security.Permissions.StrongNameIdentityPermission> hanno sempre esito positivo per gli assembly ad attendibilità totale firmati, indipendentemente dalla firma. L'unica restrizione è che l'assembly deve essere ad attendibilità totale perché la relativa area è ad attendibilità totale. Poiché il nome sicuro non è un fattore determinante in queste condizioni, non esiste alcun motivo per cui venga validato. Se la convalida di firme con nome sicuro viene ignorata, si ottengono miglioramenti significativi delle prestazioni.  
  
 La funzionalità che consente di ignorare il nome sicuro si applica a qualsiasi assembly ad attendibilità totale che non abbia la firma ritardata e che sia caricato in un oggetto <xref:System.AppDomain> ad attendibilità totale dalla directory specificata dalla proprietà <xref:System.AppDomainSetup.ApplicationBase%2A>.  
  
 È possibile ignorare questa funzionalità per tutte le applicazioni di un computer impostando il valore di una chiave del Registro di sistema. È possibile ignorare l'impostazione per una singola applicazione usando il relativo file di configurazione. Non è possibile ripristinare questa funzionalità per una singola applicazione se è stata disabilitata tramite la chiave del Registro di sistema.  
  
 Quando si ignora la funzionalità, il nome sicuro viene convalidato solo per verificare che sia corretto e non viene controllata la presenza di un oggetto <xref:System.Security.Permissions.StrongNameIdentityPermission>. Se si vuole verificare un nome sicuro specifico, è necessario eseguire il controllo separatamente.  
  
> [!IMPORTANT]
>  La possibilità per forzare la convalida del nome sicuro dipende da una chiave del Registro di sistema, come descritto nella procedura seguente. Se un'applicazione è in esecuzione con un account che non ha l'autorizzazione Elenco di controllo di accesso (ACL) per l'accesso alla chiave del Registro di sistema, l'impostazione non ha alcun effetto. Assicurarsi che siano configurati diritti ACL per la chiave in modo che sia leggibile per tutti gli assembly.  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-all-applications"></a>Per disabilitare la funzionalità che consente di ignorare il nome sicuro per tutte le applicazioni  
  
-   Nei computer a 32 bit creare nel Registro di sistema una voce DWORD con valore 0 denominata `AllowStrongNameBypass` nella chiave HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework.  
  
-   Nei computer a 64 bit creare nel Registro di sistema una voce DWORD con valore 0 denominata `AllowStrongNameBypass` nelle chiavi HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework e HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework.  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-a-single-application"></a>Per disabilitare la funzionalità che consente di ignorare il nome sicuro per una singola applicazione  
  
1. Aprire o creare il file di configurazione dell'applicazione.  
  
     Per altre informazioni su questo file, vedere la sezione File di configurazione dell'applicazione in [Configurazione delle app](../../../docs/framework/configure-apps/index.md).  
  
2. Aggiungere quanto segue:  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 È possibile ripristinare la funzionalità per l'applicazione rimuovendo l'impostazione del file di configurazione oppure impostando l'attributo su "true".  
  
> [!NOTE]
>  È possibile attivare e disattivare la convalida dei nomi sicuri per un'applicazione solo se nel computer è attivata la funzionalità che consente di ignorare il nome sicuro. Se la funzionalità è stata disattivata per il computer, i nomi sicuri vengono convalidati per tutte le applicazioni e non è possibile ignorare la convalida per una singola applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Sn.exe (strumento Nome sicuro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)
- [Elemento \<bypassTrustedAppStrongNames>](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)
- [Creazione e utilizzo degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
