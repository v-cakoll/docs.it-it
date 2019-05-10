---
title: 'Procedura: Usare modificatori e proprietà GenerateMember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211287"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="1733b-102">Procedura: Usare modificatori e proprietà GenerateMember</span><span class="sxs-lookup"><span data-stu-id="1733b-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="1733b-103">Quando si posiziona un componente in un Windows Form, dall'ambiente di progettazione vengono fornite due proprietà: `GenerateMember` e `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="1733b-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="1733b-104">Il `GenerateMember` proprietà consente di specificare quando la finestra di progettazione Windows Form genera una variabile membro per un componente.</span><span class="sxs-lookup"><span data-stu-id="1733b-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="1733b-105">Il `Modifiers` proprietà è il modificatore di accesso assegnato alla variabile membro.</span><span class="sxs-lookup"><span data-stu-id="1733b-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="1733b-106">Se il valore della `GenerateMember` proprietà è `false`, il valore della `Modifiers` proprietà non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="1733b-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="1733b-107">Specificare se un componente è un membro del form</span><span class="sxs-lookup"><span data-stu-id="1733b-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="1733b-108">In Visual Studio, nella finestra di progettazione Windows Form, aprire il form.</span><span class="sxs-lookup"><span data-stu-id="1733b-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="1733b-109">Aprire il **casella degli strumenti**e nel form, inserire tre <xref:System.Windows.Forms.Button> controlli.</span><span class="sxs-lookup"><span data-stu-id="1733b-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="1733b-110">Impostare il `GenerateMember` e `Modifiers` delle proprietà per ogni <xref:System.Windows.Forms.Button> controllo in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="1733b-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="1733b-111">Nome del pulsante</span><span class="sxs-lookup"><span data-stu-id="1733b-111">Button name</span></span>|<span data-ttu-id="1733b-112">Valore GenerateMember</span><span class="sxs-lookup"><span data-stu-id="1733b-112">GenerateMember value</span></span>|<span data-ttu-id="1733b-113">Valore di modificatori</span><span class="sxs-lookup"><span data-stu-id="1733b-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="1733b-114">Nessuna modifica</span><span class="sxs-lookup"><span data-stu-id="1733b-114">No change</span></span>|

4. <span data-ttu-id="1733b-115">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="1733b-115">Build the solution.</span></span>

5. <span data-ttu-id="1733b-116">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="1733b-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="1733b-117">Aprire il **Form1** nodo e nel **Editor di codice**, aprire il **Form1** o **Form1.Designer.cs** file.</span><span class="sxs-lookup"><span data-stu-id="1733b-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="1733b-118">Questo file contiene il codice generato da Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1733b-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="1733b-119">Trova le dichiarazioni dei tre pulsanti.</span><span class="sxs-lookup"><span data-stu-id="1733b-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="1733b-120">Esempio di codice seguente illustra le differenze specificate dal `GenerateMember` e `Modifiers` proprietà.</span><span class="sxs-lookup"><span data-stu-id="1733b-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="1733b-121">Per impostazione predefinita, la finestra di progettazione Windows Form assegna il `private` (`Friend` in Visual Basic) modifica ai controlli contenitore, ad esempio <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="1733b-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="1733b-122">Se la base <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> dispone di un controllo contenitore, non accetterà nuovi elementi figlio nei form e controlli ereditati.</span><span class="sxs-lookup"><span data-stu-id="1733b-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="1733b-123">La soluzione consiste nel modificare il modificatore del controllo contenitore di base `protected` o `public`.</span><span class="sxs-lookup"><span data-stu-id="1733b-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1733b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1733b-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="1733b-125">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1733b-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="1733b-126">Procedura dettagliata: Dimostrazione dell'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="1733b-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="1733b-127">Procedura: Ereditare Windows Form</span><span class="sxs-lookup"><span data-stu-id="1733b-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
