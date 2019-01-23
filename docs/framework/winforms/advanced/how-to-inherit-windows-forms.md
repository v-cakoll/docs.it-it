---
title: 'Procedura: Ereditare Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 29b32cd91cefe80f2f0a331f901fcabe55aa9c60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558982"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="b31c7-102">Procedura: Ereditare Windows Form</span><span class="sxs-lookup"><span data-stu-id="b31c7-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="b31c7-103">La creazione di nuovi Windows Form mediante l'ereditarietà da form di base è un modo semplice di duplicare ciò che è stato creato senza ripetere ogni volta il medesimo processo di creazione di un form.</span><span class="sxs-lookup"><span data-stu-id="b31c7-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="b31c7-104">Per altre informazioni sull'ereditarietà di form in fase di progettazione tramite le **Selezione ereditarietà** finestra di dialogo e su come distinguere visivamente i livelli di sicurezza dei controlli ereditati, vedere [come: Ereditare form mediante la finestra di dialogo Selezione ereditarietà](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="b31c7-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="b31c7-105">**Nota** per ereditare da un modulo, il file o lo spazio dei nomi contenente tale form deve essere incorporato in un file eseguibile o DLL.</span><span class="sxs-lookup"><span data-stu-id="b31c7-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="b31c7-106">Per compilare il progetto, scegliere **Compila** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="b31c7-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="b31c7-107">È necessario aggiungere un riferimento allo spazio dei nomi anche alla classe che eredita il form.</span><span class="sxs-lookup"><span data-stu-id="b31c7-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="b31c7-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="b31c7-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b31c7-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b31c7-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b31c7-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b31c7-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="b31c7-111">Per ereditare un form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="b31c7-111">To inherit a form programmatically</span></span>  
  
1.  <span data-ttu-id="b31c7-112">All'interno della classe aggiungere un riferimento allo spazio dei nomi che contiene il form da cui si vuole ereditare.</span><span class="sxs-lookup"><span data-stu-id="b31c7-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2.  <span data-ttu-id="b31c7-113">Nella definizione della classe aggiungere un riferimento al form da cui ereditare.</span><span class="sxs-lookup"><span data-stu-id="b31c7-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="b31c7-114">Il riferimento deve includere lo spazio dei nomi che contiene il form, seguito da un punto, quindi il nome del form di base.</span><span class="sxs-lookup"><span data-stu-id="b31c7-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="b31c7-115">Quando si ereditano i form, tenere presente che possono insorgere problemi relativi alla doppia chiamata a gestori eventi, perché ogni evento viene gestito sia dalla classe di base che dalla classe ereditata.</span><span class="sxs-lookup"><span data-stu-id="b31c7-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="b31c7-116">Per informazioni su come evitare questo problema, vedere [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="b31c7-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31c7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b31c7-117">See also</span></span>
- [<span data-ttu-id="b31c7-118">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="b31c7-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="b31c7-119">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="b31c7-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="b31c7-120">using</span><span class="sxs-lookup"><span data-stu-id="b31c7-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="b31c7-121">Effetti della modifica dell'aspetto di un modulo di base</span><span class="sxs-lookup"><span data-stu-id="b31c7-121">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="b31c7-122">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b31c7-122">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
