---
title: Download del pacchetto del gestore del token Web JSON
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: 3
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d3821ff1da945df7c6e07e5baf69730173eacc87
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="downloading-the-json-web-token-handler-package"></a>Download del pacchetto del gestore del token Web JSON
Questo argomento illustra come scaricare e usare il gestore del token JSON Web nel progetto.  
  
## <a name="downloading-the-json-web-token-handler"></a>Download del gestore del token Web JSON  
 L'estensione del gestore del token JSON Web è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari. Se NuGet non è ancora installato, andare a [nuget.org](http://nuget.org) per installarlo. Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/) (Gestore del token JSON Web su NuGet)  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a>Download del gestore del token JSON Web tramite l'interfaccia utente grafica di Gestione pacchetti  
  
1.  In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.  
  
2.  Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `JWT Token Handler` e premere **INVIO**.  
  
3.  Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.  
  
4.  Verrà avviato il download del pacchetto. Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza. Se si accettano le condizioni di licenza, fare clic su **Accetto**.  
  
5.  Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a>Download del gestore del token JSON Web tramite la console di Gestione pacchetti  
  
1.  In Visual Studio fare clic su **Strumenti**, quindi su **Library Package Manager** (Gestione pacchetti libreria) e infine su **Console di Gestione pacchetti**.  
  
2.  Verrà visualizzata la **Console di Gestione pacchetti**. Immettere il testo seguente e premere **INVIO**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.

