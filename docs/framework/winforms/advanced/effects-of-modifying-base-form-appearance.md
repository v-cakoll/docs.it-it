---
title: Effetti della modifica dell'aspetto di un form di base
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: adaf9224fd340c6ea4342e2591806a7c877e83ff
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084409"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="a2d4d-102">Effetti della modifica dell'aspetto di un form di base</span><span class="sxs-lookup"><span data-stu-id="a2d4d-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="a2d4d-103">Durante lo sviluppo di applicazioni, spesso potrebbe essere necessario modificare l'aspetto del form di base da cui ereditano altri form nel progetto (o in altri progetti).</span><span class="sxs-lookup"><span data-stu-id="a2d4d-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="a2d4d-104">In fase di progettazione, le modifiche all'aspetto del form di base, relative sia all'impostazione di proprietà o all'aggiunta e sottrazione dei controlli, vengono applicate ai form ereditati quando viene compilato il progetto contenente il form di base.</span><span class="sxs-lookup"><span data-stu-id="a2d4d-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="a2d4d-105">Non è sufficiente salvare le modifiche al form di base.</span><span class="sxs-lookup"><span data-stu-id="a2d4d-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="a2d4d-106">Per compilare un progetto, scegliere **Compila** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a2d4d-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2d4d-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="a2d4d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a2d4d-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="a2d4d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a2d4d-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a2d4d-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="a2d4d-110">Le modifiche apportate al form di base in fase di esecuzione non avranno alcun effetto sui form ereditati in cui è già stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a2d4d-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d4d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2d4d-111">See Also</span></span>  
 [<span data-ttu-id="a2d4d-112">base</span><span class="sxs-lookup"><span data-stu-id="a2d4d-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="a2d4d-113">Procedura: ereditare Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2d4d-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="a2d4d-114">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a2d4d-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
