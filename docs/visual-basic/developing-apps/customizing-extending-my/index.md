---
title: Personalizzazione di progetti ed estensione di oggetti My in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: 97933a9d014a54d5b6e333090cddccace99fcc3c
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960948"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="f548d-102">Personalizzazione di progetti ed estensione di oggetti My in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f548d-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="f548d-103">È possibile personalizzare i modelli di progetto per fornire oggetti `My` aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f548d-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="f548d-104">Questo consente agli altri sviluppatori di trovare e usare gli oggetti in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="f548d-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f548d-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f548d-105">In this section</span></span>

- [<span data-ttu-id="f548d-106">Estensione dello spazio dei nomi My in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f548d-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="f548d-107">Viene descritto come aggiungere membri e valori personalizzati allo spazio dei nomi `My` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f548d-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="f548d-108">Assemblaggio e distribuzione delle estensioni My personalizzate</span><span class="sxs-lookup"><span data-stu-id="f548d-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="f548d-109">Viene descritto come pubblicare estensioni dello spazio dei nomi `My` personalizzate utilizzando i modelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f548d-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="f548d-110">Estensione del modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f548d-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="f548d-111">Viene descritto come specificare estensioni personalizzate per il modello di applicazione eseguendo l'override dei membri della classe <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.</span><span class="sxs-lookup"><span data-stu-id="f548d-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="f548d-112">Personalizzazione degli oggetti disponibili in My</span><span class="sxs-lookup"><span data-stu-id="f548d-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="f548d-113">Viene descritto come controllare quali oggetti `My` sono abilitati impostando la costante di compilazione condizionale \_MYTYPE del progetto.</span><span class="sxs-lookup"><span data-stu-id="f548d-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f548d-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f548d-114">Related sections</span></span>

- [<span data-ttu-id="f548d-115">Sviluppo con My</span><span class="sxs-lookup"><span data-stu-id="f548d-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="f548d-116">Descrive quali oggetti di `My` sono disponibili in diversi tipi di progetto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f548d-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="f548d-117">Cenni preliminari sul modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f548d-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="f548d-118">Viene descritto il modello di Visual Basic per controllare il comportamento delle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f548d-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="f548d-119">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="f548d-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="f548d-120">Descrive quali oggetti di `My` sono disponibili in diversi tipi di progetto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f548d-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="f548d-121">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="f548d-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="f548d-122">Viene illustrato il modo in cui il compilatore utilizza la compilazione condizionale per selezionare sezioni specifiche di codice per compilare ed escludere altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="f548d-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="f548d-123">Descrive l'oggetto `My` che fornisce proprietà, metodi ed eventi correlati all'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="f548d-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="f548d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f548d-124">See also</span></span>

- [<span data-ttu-id="f548d-125">Sviluppo di applicazioni con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f548d-125">Developing Applications with Visual Basic</span></span>](../index.md)
