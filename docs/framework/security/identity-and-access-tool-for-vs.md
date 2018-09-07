---
title: Identity and Access Tool per Visual Studio 2012
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6af769c0b5afd61015b80c3f6987c8062c596929
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085173"
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a>Identity and Access Tool per Visual Studio 2012
In questo argomento viene descritto il nuovo strumento Identity and Access Tool for Visual Studio 11 È possibile scaricare questo strumento dal seguente URL: [ https://go.microsoft.com/fwlink/?LinkID=245849 ](https://go.microsoft.com/fwlink/?LinkID=245849) o direttamente da Visual Studio 11 cercando "identità" in Gestione estensioni.  
  
 Identity and Access Tool for Visual Studio 11 offre un'esperienza notevolmente semplificata in fase di sviluppo con le caratteristiche principali seguenti:  
  
-   Con il nuovo strumento è possibile eseguire lo sviluppo utilizzando tipi di progetto di applicazioni Web e IIS Express di destinazione.  
  
-   A differenza dell'autenticazione di sola protezione generale, con il nuovo strumento è possibile specificare la pagina o il controller di individuazione dell'area di autenticazione principale locale (o qualsiasi altro endpoint tramite cui viene gestita l'esperienza di autenticazione nell'applicazione) e tramite WIF tutte le richieste non autenticate verranno indirizzate a questo controller o pagina, anziché al servizio token di sicurezza.  
  
-   Nello strumento è incluso un servizio token di sicurezza del test che viene eseguito nel computer locale quando si avvia una sessione di debug. Pertanto, non sarà più necessario creare progetti STS personalizzati, né modificarli per ottenere le attestazioni necessarie per eseguire il test delle applicazioni. I tipi e i valori delle attestazioni sono completamente personalizzabili.  
  
-   È possibile modificare le impostazioni comuni direttamente mediante l'interfaccia utente dello strumento, senza dover modificare il file web.config.  
  
-   È possibile stabilire la federazione con Active Directory Federation Services (AD FS) 2.0, o altri provider di WS-Federation, in una singola schermata.  
  
-   Tramite lo strumento vengono utilizzate le funzionalità del Servizio di controllo di accesso (ACS) di Microsoft Azure con un elenco semplice di caselle di controllo per tutti i provider di identità che si desidera utilizzare: Facebook, Google, Live ID, Yahoo!, qualsiasi provider di OpenID e qualsiasi provider di WS-Federation. Selezionare i provider di identità, scegliere OK, quindi F5. In questo modo sia l'applicazione sia ACS verranno configurati automaticamente e l'applicazione di test sarà in grado di riconoscere ACS.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzionalità di WIF](../../../docs/framework/security/wif-features.md)
