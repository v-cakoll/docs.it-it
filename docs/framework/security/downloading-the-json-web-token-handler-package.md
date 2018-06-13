---
title: Download del pacchetto del gestore del token Web JSON
ms.date: 03/30/2017
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 5a4846a5ec92324105f41b320d0d77f8749c28f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404677"
---
# <a name="downloading-the-json-web-token-handler-package"></a><span data-ttu-id="f107b-102">Download del pacchetto del gestore del token Web JSON</span><span class="sxs-lookup"><span data-stu-id="f107b-102">Downloading the JSON Web Token Handler Package</span></span>
<span data-ttu-id="f107b-103">Questo argomento illustra come scaricare e usare il gestore del token JSON Web nel progetto.</span><span class="sxs-lookup"><span data-stu-id="f107b-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>  
  
## <a name="downloading-the-json-web-token-handler"></a><span data-ttu-id="f107b-104">Download del gestore del token Web JSON</span><span class="sxs-lookup"><span data-stu-id="f107b-104">Downloading the JSON Web Token Handler</span></span>  
 <span data-ttu-id="f107b-105">L'estensione del gestore del token JSON Web è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari.</span><span class="sxs-lookup"><span data-stu-id="f107b-105">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="f107b-106">Se NuGet non è ancora installato, andare a [nuget.org](http://nuget.org) per installarlo.</span><span class="sxs-lookup"><span data-stu-id="f107b-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="f107b-107">Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/) (Gestore del token JSON Web su NuGet)</span><span class="sxs-lookup"><span data-stu-id="f107b-107">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a><span data-ttu-id="f107b-108">Download del gestore del token JSON Web tramite l'interfaccia utente grafica di Gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="f107b-108">Downloading the JSON Web Token Handler by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="f107b-109">In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f107b-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="f107b-110">Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `JWT Token Handler` e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="f107b-110">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="f107b-111">Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.</span><span class="sxs-lookup"><span data-stu-id="f107b-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="f107b-112">Verrà avviato il download del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f107b-112">The package will begin downloading.</span></span> <span data-ttu-id="f107b-113">Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza.</span><span class="sxs-lookup"><span data-stu-id="f107b-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="f107b-114">Se si accettano le condizioni di licenza, fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="f107b-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="f107b-115">Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="f107b-115">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a><span data-ttu-id="f107b-116">Download del gestore del token JSON Web tramite la console di Gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="f107b-116">Downloading the JSON Web Token Handler by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="f107b-117">In Visual Studio fare clic su **Strumenti**, quindi su **Library Package Manager** (Gestione pacchetti libreria) e infine su **Console di Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="f107b-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="f107b-118">Verrà visualizzata la **Console di Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="f107b-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="f107b-119">Immettere il testo seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="f107b-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  <span data-ttu-id="f107b-120">Gli assembly più recenti del gestore del token JSON Web verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="f107b-120">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>
