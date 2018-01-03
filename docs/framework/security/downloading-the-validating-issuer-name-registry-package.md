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
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="35d6a-102">Download del pacchetto del registro dei nomi delle autorità emittenti</span><span class="sxs-lookup"><span data-stu-id="35d6a-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="35d6a-103">Questo argomento illustra come scaricare e usare la convalida del registro dei nomi delle autorità emittenti (VINR, Validating Issuer Name Registry) nel progetto.</span><span class="sxs-lookup"><span data-stu-id="35d6a-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="35d6a-104">Download della convalida del registro dei nomi delle autorità emittenti</span><span class="sxs-lookup"><span data-stu-id="35d6a-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="35d6a-105">VINR è disponibile come pacchetto NuGet, che aggiunge al progetto gli assembly e i riferimenti necessari.</span><span class="sxs-lookup"><span data-stu-id="35d6a-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="35d6a-106">Se NuGet non è ancora installato, andare a [nuget.org](http://nuget.org) per installarlo.</span><span class="sxs-lookup"><span data-stu-id="35d6a-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="35d6a-107">Per visualizzare la cronologia del controllo delle versioni per l'estensione, visitare la pagina su NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/) (Convalida del registro dei nomi delle autorità emittenti Microsoft su NuGet)</span><span class="sxs-lookup"><span data-stu-id="35d6a-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="35d6a-108">Download della convalida del registro dei nomi delle autorità emittenti tramite l'interfaccia utente grafica di Gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="35d6a-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="35d6a-109">In Visual Studio fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e quindi scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="35d6a-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="35d6a-110">Nella finestra **Gestisci pacchetti NuGet** fare clic sulla casella di ricerca, immettere `ValidatingIssuerNameRegistry` e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="35d6a-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="35d6a-111">Nel riquadro dei dettagli fare clic sul pulsante **Installa** per il primo risultato.</span><span class="sxs-lookup"><span data-stu-id="35d6a-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="35d6a-112">Verrà avviato il download del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="35d6a-112">The package will begin downloading.</span></span> <span data-ttu-id="35d6a-113">Prima che venga aggiunto al progetto, verrà visualizzata la finestra di dialogo Accettazione della licenza.</span><span class="sxs-lookup"><span data-stu-id="35d6a-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="35d6a-114">Se si accettano le condizioni di licenza, fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="35d6a-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="35d6a-115">Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="35d6a-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="35d6a-116">Download della convalida del registro dei nomi delle autorità emittenti tramite la console di Gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="35d6a-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="35d6a-117">In Visual Studio fare clic su **Strumenti**, quindi su **Library Package Manager** (Gestione pacchetti libreria) e infine su **Console di Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="35d6a-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="35d6a-118">Verrà visualizzata la **Console di Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="35d6a-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="35d6a-119">Immettere il testo seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="35d6a-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="35d6a-120">Gli assembly VINR più recenti verranno scaricati e aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="35d6a-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
