---
title: 'Procedura: Rendere invisibile il controllo in fase di esecuzione'
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
ms.openlocfilehash: 06283a93c3b88d2febc1d64797139eee62661b42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201650"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="7a175-102">Procedura: Rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="7a175-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="7a175-103">Vi sono casi quando si potrebbe voler creare un controllo utente che non è visibile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7a175-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="7a175-104">Ad esempio, potrebbe essere invisibile tranne quando l'allarme è stato suona un controllo che una sveglia.</span><span class="sxs-lookup"><span data-stu-id="7a175-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="7a175-105">Questo avviene facilmente impostando il <xref:System.Windows.Forms.Control.Visible%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a175-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="7a175-106">Se il <xref:System.Windows.Forms.Control.Visible%2A> è di proprietà `true`, il controllo verrà visualizzato come di consueto.</span><span class="sxs-lookup"><span data-stu-id="7a175-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="7a175-107">Se `false`, il controllo sarà nascosto.</span><span class="sxs-lookup"><span data-stu-id="7a175-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="7a175-108">Anche se nel controllo del codice può comunque eseguire nonostante sia invisibile, non sarà in grado di interagire con il controllo tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="7a175-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="7a175-109">Se si desidera creare un controllo invisibile in grado di rispondere all'input (ad esempio, clic del mouse) dell'utente, è necessario creare un controllo trasparente.</span><span class="sxs-lookup"><span data-stu-id="7a175-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="7a175-110">Per altre informazioni, vedere [assegnazione di uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="7a175-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="7a175-111">Per rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="7a175-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="7a175-112">Impostare la proprietà <xref:System.Windows.Forms.Control.Visible%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="7a175-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7a175-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a175-113">See also</span></span>

- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="7a175-114">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a175-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="7a175-115">Procedura: Assegnare uno sfondo trasparente al controllo</span><span class="sxs-lookup"><span data-stu-id="7a175-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)
