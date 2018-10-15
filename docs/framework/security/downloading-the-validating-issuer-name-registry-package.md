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
# <a name="download-the-validating-issuer-name-registry-package"></a><span data-ttu-id="c8262-102">Scaricare il pacchetto del Registro di sistema durante la convalida del nome dell'autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="c8262-102">Download the Validating Issuer Name Registry Package</span></span>

<span data-ttu-id="c8262-103">Questo argomento illustra come scaricare e usare la convalida del registro dei nomi delle autorità emittenti (VINR, Validating Issuer Name Registry) nel progetto.</span><span class="sxs-lookup"><span data-stu-id="c8262-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>

<span data-ttu-id="c8262-104">VINR è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari.</span><span class="sxs-lookup"><span data-stu-id="c8262-104">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="c8262-105">Se NuGet non è ancora installato, andare a [nuget.org](https://nuget.org) per installarlo.</span><span class="sxs-lookup"><span data-stu-id="c8262-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="c8262-106">Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/) (Convalida del registro dei nomi delle autorità emittenti Microsoft su NuGet)</span><span class="sxs-lookup"><span data-stu-id="c8262-106">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="c8262-107">Utilizzare la GUI di gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="c8262-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="c8262-108">In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c8262-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="c8262-109">Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `ValidatingIssuerNameRegistry` e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="c8262-109">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>

3. <span data-ttu-id="c8262-110">Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.</span><span class="sxs-lookup"><span data-stu-id="c8262-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="c8262-111">Verrà avviato il download del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c8262-111">The package will begin downloading.</span></span> <span data-ttu-id="c8262-112">Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza.</span><span class="sxs-lookup"><span data-stu-id="c8262-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="c8262-113">Se si accettano le condizioni di licenza, fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="c8262-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="c8262-114">Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="c8262-114">The latest VINR assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="c8262-115">Utilizzare la Console di gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="c8262-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="c8262-116">In Visual Studio, fare clic su **degli strumenti** > **Gestione pacchetti NuGet** > **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="c8262-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="c8262-117">Verrà visualizzata la **Console di Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="c8262-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="c8262-118">Immettere il testo seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="c8262-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. <span data-ttu-id="c8262-119">Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="c8262-119">The latest VINR assemblies will be downloaded and added to your project.</span></span>