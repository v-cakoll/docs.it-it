---
title: 'Procedura: rendere invisibile il controllo in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: 51e804c7f01b55ed7504837042b6c32bf47d9405
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532412"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="cd3ae-102">Procedura: rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="cd3ae-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="cd3ae-103">Vi sono casi quando si potrebbe desiderare di creare un controllo utente che non è visibile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="cd3ae-104">Ad esempio, potrebbe essere invisibile tranne quando l'avviso è stato emissione di un controllo che una sveglia.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="cd3ae-105">A tal fine, impostare il <xref:System.Windows.Forms.Control.Visible%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="cd3ae-106">Se il <xref:System.Windows.Forms.Control.Visible%2A> proprietà `true`, il controllo verrà visualizzato come di consueto.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="cd3ae-107">Se `false`, il controllo verrà nascosto.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="cd3ae-108">Anche se il controllo del codice può comunque eseguire invisibili, non sarà in grado di interagire con il controllo tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="cd3ae-109">Se si desidera creare un controllo invisibile in grado di rispondere all'input (ad esempio, clic del mouse) dell'utente, è necessario creare un controllo trasparente.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="cd3ae-110">Per ulteriori informazioni, vedere [assegnazione di uno sfondo trasparente al controllo](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="cd3ae-110">For more information, see [Giving Your Control a Transparent Background](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="cd3ae-111">Per rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="cd3ae-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="cd3ae-112">Impostare la proprietà <xref:System.Windows.Forms.Control.Visible%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="cd3ae-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cd3ae-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd3ae-113">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [<span data-ttu-id="cd3ae-114">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cd3ae-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="cd3ae-115">Procedura: Assegnare uno sfondo trasparente al controllo</span><span class="sxs-lookup"><span data-stu-id="cd3ae-115">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
