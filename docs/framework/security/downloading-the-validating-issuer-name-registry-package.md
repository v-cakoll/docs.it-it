---
title: Download del pacchetto del registro dei nomi delle autorità emittenti
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 833a0722fdd27df4e488ed7fac99444c6d9b8905
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316188"
---
# <a name="download-the-validating-issuer-name-registry-package"></a>Scaricare il pacchetto del Registro di sistema durante la convalida del nome dell'autorità di certificazione

Questo argomento illustra come scaricare e usare la convalida del registro dei nomi delle autorità emittenti (VINR, Validating Issuer Name Registry) nel progetto.

VINR è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari. Se NuGet non è ancora installato, andare a [nuget.org](https://nuget.org) per installarlo. Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/) (Convalida del registro dei nomi delle autorità emittenti Microsoft su NuGet)

## <a name="use-the-package-manager-gui"></a>Utilizzare la GUI di gestione pacchetti

1. In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.

2. Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `ValidatingIssuerNameRegistry` e premere **INVIO**.

3. Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.

4. Verrà avviato il download del pacchetto. Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza. Se si accettano le condizioni di licenza, fare clic su **Accetto**.

5. Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.

## <a name="use-the-package-manager-console"></a>Utilizzare la Console di gestione pacchetti

1. In Visual Studio, fare clic su **degli strumenti** > **Gestione pacchetti NuGet** > **Package Manager Console**.

2. Verrà visualizzata la **Console di Gestione pacchetti**. Immettere il testo seguente e premere **INVIO**:

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.