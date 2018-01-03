---
title: "Download del pacchetto del registro dei nomi delle autorità emittenti"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bf6869de939ed7eda7cd3de868e712126f71751
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a>Download del pacchetto del registro dei nomi delle autorità emittenti
Questo argomento illustra come scaricare e usare la convalida del registro dei nomi delle autorità emittenti (VINR, Validating Issuer Name Registry) nel progetto.  
  
## <a name="downloading-the-validating-issuer-name-registry"></a>Download della convalida del registro dei nomi delle autorità emittenti  
 VINR è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari. Se NuGet non è ancora installato, andare a [nuget.org](http://nuget.org) per installarlo. Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/) (Convalida del registro dei nomi delle autorità emittenti Microsoft su NuGet)  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a>Download della convalida del registro dei nomi delle autorità emittenti tramite l'interfaccia utente grafica di Gestione pacchetti  
  
1.  In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.  
  
2.  Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `ValidatingIssuerNameRegistry` e premere **INVIO**.  
  
3.  Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.  
  
4.  Verrà avviato il download del pacchetto. Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza. Se si accettano le condizioni di licenza, fare clic su **Accetto**.  
  
5.  Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a>Download della convalida del registro dei nomi delle autorità emittenti tramite la console di Gestione pacchetti  
  
1.  In Visual Studio fare clic su **Strumenti**, quindi su **Library Package Manager** (Gestione pacchetti libreria) e infine su **Console di Gestione pacchetti**.  
  
2.  Verrà visualizzata la **Console di Gestione pacchetti**. Immettere il testo seguente e premere **INVIO**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.
