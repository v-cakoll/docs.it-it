---
title: 'Procedura: Impostare la maschera di input'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06eaf68fef167d63e6f8404dd5049f5445881d24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331468"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="79b7f-102">Procedura: Impostare la maschera di input</span><span class="sxs-lookup"><span data-stu-id="79b7f-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="79b7f-103">Il controllo casella di testo mascherata è un controllo casella di testo avanzato che supporta una sintassi dichiarativa per accettare o rifiutare l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="79b7f-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="79b7f-104">Impostando la proprietà Mask, è possibile specificare l'input dell'utente consentita senza scrivere una logica di convalida personalizzato nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79b7f-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="79b7f-105">Per altre informazioni, vedere la sezione Osservazioni del <xref:System.Windows.Forms.MaskedTextBox> classe.</span><span class="sxs-lookup"><span data-stu-id="79b7f-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="79b7f-106">Impostare la proprietà Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="79b7f-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="79b7f-107">Se si ha familiarità con i caratteri che supporta la proprietà Mask, è possibile immetterlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="79b7f-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="79b7f-108">Per un riepilogo dei caratteri che supporta la proprietà Mask, vedere la sezione Osservazioni del <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="79b7f-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="79b7f-109">Per impostare la proprietà Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="79b7f-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="79b7f-110">Nelle **Design** visualizzazione, selezionare un <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="79b7f-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="79b7f-111">Nel **delle proprietà** finestra, individuare il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="79b7f-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="79b7f-112">Tipo di maschera che si desidera.</span><span class="sxs-lookup"><span data-stu-id="79b7f-112">Type the mask that you want.</span></span> <span data-ttu-id="79b7f-113">Ad esempio, digitare `###`.</span><span class="sxs-lookup"><span data-stu-id="79b7f-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="79b7f-114">Nella finestra di dialogo maschera di Input</span><span class="sxs-lookup"><span data-stu-id="79b7f-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="79b7f-115">La finestra di dialogo di maschera di Input offre alcune maschere di input predefinite.</span><span class="sxs-lookup"><span data-stu-id="79b7f-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="79b7f-116">È anche possibile modificare le maschere predefinite o immettere manualmente il proprio filtro.</span><span class="sxs-lookup"><span data-stu-id="79b7f-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="79b7f-117">Per aprire la finestra di dialogo di maschera di Input</span><span class="sxs-lookup"><span data-stu-id="79b7f-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="79b7f-118">Nelle **Design** visualizzazione, selezionare un <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="79b7f-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="79b7f-119">Clic sullo smart tag per aprire la **MaskedTextBox attività** pannello.</span><span class="sxs-lookup"><span data-stu-id="79b7f-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="79b7f-120">Fare clic su **Imposta maschera**.</span><span class="sxs-lookup"><span data-stu-id="79b7f-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="79b7f-121">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="79b7f-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="79b7f-122">Nel **delle proprietà** finestra, seleziona il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="79b7f-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="79b7f-123">Fare clic sui puntini di sospensione nella colonna valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="79b7f-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="79b7f-124">Il **maschera di Input** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79b7f-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="79b7f-125">Usare la finestra di dialogo di maschera di Input</span><span class="sxs-lookup"><span data-stu-id="79b7f-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="79b7f-126">(Facoltativo) Fare clic su una delle maschere predefinite nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="79b7f-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="79b7f-127">(Facoltativo) Modificare la maschera predefinita in di **Mask** casella.</span><span class="sxs-lookup"><span data-stu-id="79b7f-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="79b7f-128">(Facoltativo) Digitare una nuova maschera nel **Mask** casella.</span><span class="sxs-lookup"><span data-stu-id="79b7f-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="79b7f-129">Vale a dire, non è necessario usare una delle maschere predefinite.</span><span class="sxs-lookup"><span data-stu-id="79b7f-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79b7f-130">La finestra di anteprima vengono visualizzati i caratteri che l'utente vede nel <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="79b7f-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="79b7f-131">Questi caratteri sono una Guida che consente all'utente di immettere correttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="79b7f-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="79b7f-132">Selezionare o deselezionare i **utilizza ValidatingType** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="79b7f-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="79b7f-133">Il **utilizza ValidatingType** casella di controllo specifica se un tipo di dati viene utilizzato per verificare l'input di dati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="79b7f-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="79b7f-134">Per altre informazioni, vedere la proprietà <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="79b7f-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="79b7f-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79b7f-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="79b7f-136">La maschera viene immesso nel **maschera** proprietà nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="79b7f-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b7f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b7f-137">See also</span></span>

- [<span data-ttu-id="79b7f-138">Procedura dettagliata: Utilizzo del controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="79b7f-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
