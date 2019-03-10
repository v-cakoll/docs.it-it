---
title: Ereditarietà visiva di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
ms.openlocfilehash: e94cdc38b97f95cfe8a8504733298525c25667df
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705298"
---
# <a name="windows-forms-visual-inheritance"></a><span data-ttu-id="978a9-102">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="978a9-102">Windows Forms Visual Inheritance</span></span>
<span data-ttu-id="978a9-103">In alcuni casi è possibile impostare un progetto in modo che richiami un modulo simile a uno creato in un progetto precedente.</span><span class="sxs-lookup"><span data-stu-id="978a9-103">Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project.</span></span> <span data-ttu-id="978a9-104">In altri casi, può rivelarsi utile creare un modulo di base con impostazioni quali una filigrana o il layout di un determinato controllo da usare successivamente all'interno di un progetto, con modifiche al modello del modulo originale contenute in ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="978a9-104">Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template.</span></span> <span data-ttu-id="978a9-105">L'ereditarietà dei moduli consente di creare un modulo di base e di ereditare da tale modulo, quindi di apportare modifiche conservando le impostazioni originali necessarie.</span><span class="sxs-lookup"><span data-stu-id="978a9-105">Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.</span></span>  
  
 <span data-ttu-id="978a9-106">È possibile creare moduli che derivano da classi a livello di codice oppure mediante la finestra di selezione dell'ereditarietà visiva.</span><span class="sxs-lookup"><span data-stu-id="978a9-106">You can create derived-class forms programmatically or by using the Visual Inheritance picker.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="978a9-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="978a9-107">In This Section</span></span>  
 [<span data-ttu-id="978a9-108">Procedura: Ereditare Windows Form</span><span class="sxs-lookup"><span data-stu-id="978a9-108">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)  
 <span data-ttu-id="978a9-109">Vengono fornite indicazioni per creare nel codice moduli ereditati.</span><span class="sxs-lookup"><span data-stu-id="978a9-109">Gives directions for creating inherited forms in code.</span></span>  
  
 [<span data-ttu-id="978a9-110">Procedura: Ereditare form mediante la finestra di dialogo Selezione ereditarietà</span><span class="sxs-lookup"><span data-stu-id="978a9-110">How to: Inherit Forms Using the Inheritance Picker Dialog Box</span></span>](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 <span data-ttu-id="978a9-111">Vengono fornite indicazioni per creare form ereditati mediante la finestra di selezione dell'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="978a9-111">Gives directions for creating inherited forms with the Inheritance Picker.</span></span>  
  
 [<span data-ttu-id="978a9-112">Effetti della modifica dell'aspetto di un modulo di base</span><span class="sxs-lookup"><span data-stu-id="978a9-112">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)  
 <span data-ttu-id="978a9-113">Vengono fornite indicazioni per modificare i controlli di un modulo di base e le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="978a9-113">Gives directions for changing a base form's controls and their properties.</span></span>  
  
 [<span data-ttu-id="978a9-114">Procedura dettagliata: Dimostrazione dell'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="978a9-114">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)  
 <span data-ttu-id="978a9-115">Viene descritta la creazione di un Windows Form di base e la relativa compilazione in una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="978a9-115">Describes how to create a base Windows Form and compile it into a class library.</span></span> <span data-ttu-id="978a9-116">La libreria di classi verrà importata in un altro progetto e verrà creato un nuovo modulo che eredita dal modulo di base.</span><span class="sxs-lookup"><span data-stu-id="978a9-116">You will import this class library into another project, and create a new form that inherits from the base form.</span></span>  
  
 [<span data-ttu-id="978a9-117">Procedura: Usare i modificatori e proprietà GenerateMember</span><span class="sxs-lookup"><span data-stu-id="978a9-117">How to: Use the Modifiers and GenerateMember Properties</span></span>](how-to-use-the-modifiers-and-generatemember-properties.md)  
 <span data-ttu-id="978a9-118">Vengono fornite indicazioni per l'utilizzo delle proprietà `GenerateMember` e `Modifiers`, che sono pertinenti quando in Progettazione Windows Form viene generata una variabile membro per un componente.</span><span class="sxs-lookup"><span data-stu-id="978a9-118">Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="978a9-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="978a9-119">Related Sections</span></span>  
 [<span data-ttu-id="978a9-120">Nozioni fondamentali sull'ereditarietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="978a9-120">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 <span data-ttu-id="978a9-121">Vengono descritte le modalità di definizione delle classi Visual Basic che fungono da base per altre classi.</span><span class="sxs-lookup"><span data-stu-id="978a9-121">Describes how to define Visual Basic classes that serve as the basis for other classes.</span></span>  
  
 [<span data-ttu-id="978a9-122">class</span><span class="sxs-lookup"><span data-stu-id="978a9-122">class</span></span>](~/docs/csharp/language-reference/keywords/class.md)  
 <span data-ttu-id="978a9-123">Viene descritto l'approccio di C# alle classi in cui è consentita l'ereditarietà singola.</span><span class="sxs-lookup"><span data-stu-id="978a9-123">Describes the C# approach of classes, in which single inheritance is allowed.</span></span>  
  
 [<span data-ttu-id="978a9-124">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="978a9-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="978a9-125">Vengono elencati problemi comuni relativi ai gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="978a9-125">Lists common issues that arise with event handlers in inherited components</span></span>
