---
title: 'Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: db4b3ac020e967a6a0c291103d825ac71cebda23
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458277"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="874b3-102">Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="874b3-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>

<span data-ttu-id="874b3-103">Quando si sviluppano e si distribuiscono i controlli, è possibile che tali controlli siano visualizzati nella finestra di dialogo **Scegli elementi della casella degli strumenti** di Visual Studio, che viene visualizzato quando si fa clic con il pulsante destro del mouse sulla **casella degli strumenti** e si seleziona **Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="874b3-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box of Visual Studio, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="874b3-104">È possibile abilitare il controllo per la visualizzazione in questa finestra di dialogo tramite la procedura di registrazione AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="874b3-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>

<span data-ttu-id="874b3-105">Per visualizzare il controllo nella finestra di dialogo Scegli elementi della casella degli strumenti:</span><span class="sxs-lookup"><span data-stu-id="874b3-105">To display your control in the Choose Toolbox Items dialog box:</span></span>

- <span data-ttu-id="874b3-106">Installare l'assembly di controllo nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="874b3-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="874b3-107">Per altre informazioni, vedere [Procedura: installare un assembly nella Global Assembly Cache](../../app-domains/install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="874b3-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/install-assembly-into-gac.md).</span></span>

  <span data-ttu-id="874b3-108">oppure</span><span class="sxs-lookup"><span data-stu-id="874b3-108">-or-</span></span>

- <span data-ttu-id="874b3-109">Registrare il controllo e gli assembly in fase di progettazione associati tramite la procedura di registrazione AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="874b3-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="874b3-110">AssemblyFoldersEx è un percorso del registro di sistema in cui i fornitori di terze parti archiviano percorsi per ogni versione del Framework supportata.</span><span class="sxs-lookup"><span data-stu-id="874b3-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="874b3-111">La risoluzione in fase di progettazione può essere esaminata nel percorso del registro di sistema per trovare gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="874b3-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="874b3-112">Lo script del registro di sistema può specificare i controlli che si desidera visualizzare nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="874b3-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="874b3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="874b3-113">See also</span></span>

- [<span data-ttu-id="874b3-114">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="874b3-114">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="874b3-115">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="874b3-115">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/install-assembly-into-gac.md)
- [<span data-ttu-id="874b3-116">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="874b3-116">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
