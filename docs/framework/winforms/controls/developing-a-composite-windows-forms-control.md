---
title: Sviluppo di un controllo Windows Form composto
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 24fbf17f02072b2d9922ca0998805b916afc41b6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510160"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="f659a-102">Sviluppo di un controllo Windows Form composto</span><span class="sxs-lookup"><span data-stu-id="f659a-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="f659a-103">È possibile sviluppare un controllo Windows Form composito combinando altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f659a-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="f659a-104">I controlli compositi che derivano da <xref:System.Web.UI.UserControl> sono denominati controlli utente.</span><span class="sxs-lookup"><span data-stu-id="f659a-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="f659a-105">La classe base, <xref:System.Windows.Forms.UserControl>, fornisce il routing della tastiera per i controlli figlio, garantendo così che i controlli figlio possano ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="f659a-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="f659a-106">Per un esempio di un controllo utente, vedere la <xref:System.Windows.Forms.UserControl> esempio nella [procedura: applicare attributi nei controlli di Windows Form](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f659a-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="f659a-107">La finestra di progettazione di Windows Form in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] fornisce supporto avanzato in fase di progettazione per la creazione di controlli utente.</span><span class="sxs-lookup"><span data-stu-id="f659a-107">The Windows Forms designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] provides rich design-time support for authoring user controls.</span></span>  
  
-   <span data-ttu-id="f659a-108">[Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-108">[How to: Display a Control in the Choose Toolbox Items Dialog Box](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span></span>  
  
-   [<span data-ttu-id="f659a-109">Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="f659a-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   <span data-ttu-id="f659a-110">[Procedura dettagliata: Eredità da un controllo Windows Form con Visual C#](https://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438)</span><span class="sxs-lookup"><span data-stu-id="f659a-110">[Walkthrough: Inheriting from a Windows Forms Control with Visual C#](https://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438))</span></span>  
  
-   <span data-ttu-id="f659a-111">[Procedura: Specificare una bitmap nella casella degli strumenti per un controllo](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-111">[How to: Provide a Toolbox Bitmap for a Control](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-112">[Procedura: ereditare da controlli Windows Form esistenti](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-112">[How to: Inherit from Existing Windows Forms Controls](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-113">[Procedura dettagliata: Debug di controlli Windows Form personalizzati in fase di progettazione](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-113">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-114">[Procedura: ereditare dalla classe Control](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-114">[How to: Inherit from the Control Class](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span></span>  
  
-   [<span data-ttu-id="f659a-115">Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="f659a-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   <span data-ttu-id="f659a-116">[Procedura: allineare un controllo ai bordi dei form in fase di progettazione](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-116">[How to: Align a Control to the Edges of Forms at Design Time](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-117">[Procedura: ereditare dalla classe UserControl](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-117">[How to: Inherit from the UserControl Class](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-118">[Procedura: creare controlli per Windows Form](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-118">[How to: Author Controls for Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-119">[Procedura: modificare controlli compositi](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-119">[How to: Author Composite Controls](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-120">[Procedura dettagliata: Modifica di un controllo composito con Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-120">[Walkthrough: Authoring a Composite Control with Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-121">[Procedura dettagliata: Modifica di un controllo composito con Visual C#](https://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f)</span><span class="sxs-lookup"><span data-stu-id="f659a-121">[Walkthrough: Authoring a Composite Control with Visual C#](https://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f))</span></span>  
  
-   <span data-ttu-id="f659a-122">[Procedura dettagliata: Eredità da un controllo Windows Form con Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-122">[Walkthrough: Inheriting from a Windows Forms Control with Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-123">[Procedura: Creare un controllo di Windows Form che sfrutta le funzionalità di progettazione](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f659a-123">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="f659a-124">[Procedura: Creare un controllo Windows Form che utilizza le funzionalità di progettazione](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="f659a-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f659a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f659a-125">See Also</span></span>  
 [<span data-ttu-id="f659a-126">Procedura: Applicare attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="f659a-126">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="f659a-127">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f659a-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="f659a-128">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="f659a-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
