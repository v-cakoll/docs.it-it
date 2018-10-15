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
# <a name="download-the-json-web-token-handler-package"></a><span data-ttu-id="1c3f3-102">Scaricare il pacchetto del gestore dei Token Web JSON</span><span class="sxs-lookup"><span data-stu-id="1c3f3-102">Download the JSON Web Token Handler Package</span></span>

<span data-ttu-id="1c3f3-103">Questo argomento illustra come scaricare e usare il gestore del token JSON Web nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>

<span data-ttu-id="1c3f3-104">L'estensione del gestore del token JSON Web è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-104">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="1c3f3-105">Se NuGet non è ancora installato, andare a [nuget.org](https://nuget.org) per installarlo.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="1c3f3-106">Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/) (Gestore del token JSON Web su NuGet)</span><span class="sxs-lookup"><span data-stu-id="1c3f3-106">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="1c3f3-107">Utilizzare la GUI di gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="1c3f3-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="1c3f3-108">In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="1c3f3-109">Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `JWT Token Handler` e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-109">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>

3. <span data-ttu-id="1c3f3-110">Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="1c3f3-111">Verrà avviato il download del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-111">The package will begin downloading.</span></span> <span data-ttu-id="1c3f3-112">Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="1c3f3-113">Se si accettano le condizioni di licenza, fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="1c3f3-114">Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-114">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="1c3f3-115">Utilizzare la Console di gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="1c3f3-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="1c3f3-116">In Visual Studio, fare clic su **degli strumenti** > **Gestione pacchetti NuGet** > **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="1c3f3-117">Verrà visualizzata la **Console di Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="1c3f3-118">Immettere il testo seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="1c3f3-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. <span data-ttu-id="1c3f3-119">Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="1c3f3-119">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>