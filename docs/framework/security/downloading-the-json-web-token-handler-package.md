---
title: Download del pacchetto del gestore del token Web JSON
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 8f878d23afd76488de7da03f16f72cbfa43c17d7
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316480"
---
# <a name="download-the-json-web-token-handler-package"></a>Scaricare il pacchetto del gestore dei Token Web JSON

Questo argomento illustra come scaricare e usare il gestore del token JSON Web nel progetto.

L'estensione del gestore del token JSON Web è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari. Se NuGet non è ancora installato, andare a [nuget.org](https://nuget.org) per installarlo. Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/) (Gestore del token JSON Web su NuGet)

## <a name="use-the-package-manager-gui"></a>Utilizzare la GUI di gestione pacchetti

1. In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.

2. Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `JWT Token Handler` e premere **INVIO**.

3. Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.

4. Verrà avviato il download del pacchetto. Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza. Se si accettano le condizioni di licenza, fare clic su **Accetto**.

5. Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.

## <a name="use-the-package-manager-console"></a>Utilizzare la Console di gestione pacchetti

1. In Visual Studio, fare clic su **degli strumenti** > **Gestione pacchetti NuGet** > **Package Manager Console**.

2. Verrà visualizzata la **Console di Gestione pacchetti**. Immettere il testo seguente e premere **INVIO**:

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.