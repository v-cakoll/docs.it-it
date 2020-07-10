---
title: "Procedura: aggiungere più set di impostazioni all'applicazione in C#"
description: Informazioni su come aggiungere più set di impostazioni Windows Forms all'applicazione in C# usando Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173445"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="5fbc4-103">Procedura: aggiungere più set di impostazioni all'applicazione in C\#</span><span class="sxs-lookup"><span data-stu-id="5fbc4-103">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="5fbc4-104">In alcuni casi, potrebbe essere necessario disporre di più set di impostazioni in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-104">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="5fbc4-105">Se, ad esempio, si sta sviluppando un'applicazione in cui si prevede che un determinato gruppo di impostazioni venga modificato di frequente, è consigliabile separarli tutti in un unico file, in modo che il file possa essere sostituito in modo inverso, lasciando inalterate le altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-105">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="5fbc4-106">Visual Studio consente di aggiungere più set di impostazioni al progetto.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-106">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="5fbc4-107">È possibile accedere a set aggiuntivi di impostazioni tramite l' `Properties.Settings` oggetto.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-107">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="5fbc4-108">Aggiungere un set aggiuntivo di impostazioni</span><span class="sxs-lookup"><span data-stu-id="5fbc4-108">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="5fbc4-109">In Visual Studio scegliere **Aggiungi nuovo elemento**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="5fbc4-109">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="5fbc4-110">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .</span><span class="sxs-lookup"><span data-stu-id="5fbc4-110">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="5fbc4-111">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **file di impostazioni**, immettere un nome per il file e fare clic su **Aggiungi** per aggiungere un nuovo file di impostazioni alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-111">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="5fbc4-112">In **Esplora soluzioni**trascinare il nuovo file di impostazioni nella cartella **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="5fbc4-112">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="5fbc4-113">In questo modo le nuove impostazioni sono disponibili nel codice.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-113">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="5fbc4-114">Aggiungere e utilizzare le impostazioni in questo file come qualsiasi altro file di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-114">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="5fbc4-115">È possibile accedere a questo gruppo di impostazioni tramite l' `Properties.Settings` oggetto.</span><span class="sxs-lookup"><span data-stu-id="5fbc4-115">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fbc4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fbc4-116">See also</span></span>

- [<span data-ttu-id="5fbc4-117">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="5fbc4-117">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="5fbc4-118">Panoramica delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5fbc4-118">Application Settings Overview</span></span>](application-settings-overview.md)
