---
title: Effetti della modifica dell'aspetto di un form di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5121238341afac46ad1c999710d51b5c203a1b6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="01b13-102">Effetti della modifica dell'aspetto di un form di base</span><span class="sxs-lookup"><span data-stu-id="01b13-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="01b13-103">Durante lo sviluppo di applicazioni, spesso potrebbe essere necessario modificare l'aspetto del form di base da cui ereditano altri form nel progetto (o in altri progetti).</span><span class="sxs-lookup"><span data-stu-id="01b13-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="01b13-104">In fase di progettazione, le modifiche all'aspetto del form di base, relative sia all'impostazione di proprietà o all'aggiunta e sottrazione dei controlli, vengono applicate ai form ereditati quando viene compilato il progetto contenente il form di base.</span><span class="sxs-lookup"><span data-stu-id="01b13-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="01b13-105">Non è sufficiente salvare le modifiche al form di base.</span><span class="sxs-lookup"><span data-stu-id="01b13-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="01b13-106">Per compilare un progetto, scegliere **Compila** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="01b13-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01b13-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="01b13-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="01b13-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="01b13-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="01b13-109">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="01b13-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
 <span data-ttu-id="01b13-110">Le modifiche apportate al form di base in fase di esecuzione non avranno alcun effetto sui form ereditati in cui è già stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="01b13-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b13-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01b13-111">See Also</span></span>  
 [<span data-ttu-id="01b13-112">base</span><span class="sxs-lookup"><span data-stu-id="01b13-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="01b13-113">Procedura: ereditare Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01b13-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="01b13-114">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="01b13-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
