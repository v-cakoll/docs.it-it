---
title: "Procedura: Aggiungere all'applicazione in più set di impostazioniC#"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 447d171cf9dbe2672ae138e9e902cbd72a206c94
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969639"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="e63f9-102">Procedura: Aggiungere più set di impostazioni dell'applicazione in C\#</span><span class="sxs-lookup"><span data-stu-id="e63f9-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>
<span data-ttu-id="e63f9-103">In alcuni casi, è consigliabile avere più set di impostazioni in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e63f9-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="e63f9-104">Ad esempio, se si sviluppa un'applicazione posto di un determinato gruppo di impostazioni di cambiare frequentemente, è possibile raggrupparle tutto in un singolo file in modo che il file può essere sostituito a livello globale, lasciando inalterate le altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e63f9-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="e63f9-105">Visual Studio consente di aggiungere più set di impostazioni al progetto.</span><span class="sxs-lookup"><span data-stu-id="e63f9-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="e63f9-106">Altri set di impostazioni sono accessibili tramite l'oggetto Properties. Settings.</span><span class="sxs-lookup"><span data-stu-id="e63f9-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="e63f9-107">Per aggiungere un ulteriore Set di impostazioni all'applicazione</span><span class="sxs-lookup"><span data-stu-id="e63f9-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="e63f9-108">Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e63f9-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="e63f9-109">Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e63f9-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="e63f9-110">Nel **Aggiungi nuovo elemento** finestra di dialogo **File di impostazioni**, digitare un nome per il file e fare clic su **Add** per aggiungere un nuovo file di impostazioni per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="e63f9-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="e63f9-111">Nelle **Esplora soluzioni**, trascinare il nuovo file di impostazioni nel **proprietà** cartella.</span><span class="sxs-lookup"><span data-stu-id="e63f9-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="e63f9-112">In questo modo le nuove impostazioni saranno disponibili nel codice.</span><span class="sxs-lookup"><span data-stu-id="e63f9-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="e63f9-113">Aggiungere e usare le impostazioni in questo file come si farebbe con qualsiasi altro file di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e63f9-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="e63f9-114">È possibile accedere a questo gruppo di impostazioni tramite l'oggetto Properties. Settings.</span><span class="sxs-lookup"><span data-stu-id="e63f9-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e63f9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e63f9-115">See also</span></span>
- [<span data-ttu-id="e63f9-116">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="e63f9-116">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="e63f9-117">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="e63f9-117">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
