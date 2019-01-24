---
title: 'Procedura: Creare un controllo che dispone di un tasto di scelta e di una disposizione di testo'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 12410e2abd1031f7ac42bdaab4b8e09a6b8b6006
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649583"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="7448e-102">Procedura: Creare un controllo che dispone di un tasto di scelta e di una disposizione di testo</span><span class="sxs-lookup"><span data-stu-id="7448e-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="7448e-103">Questo esempio illustra come creare un controllo dotato di un tasto di scelta e con un supporto di disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="7448e-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="7448e-104">Nell'esempio viene usato un <xref:System.Windows.Controls.Label> controllo per illustrare questi concetti.</span><span class="sxs-lookup"><span data-stu-id="7448e-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7448e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7448e-105">Example</span></span>  
 <span data-ttu-id="7448e-106">**Aggiungere la disposizione del testo all'etichetta**</span><span class="sxs-lookup"><span data-stu-id="7448e-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="7448e-107">Il <xref:System.Windows.Controls.Label> controllo non supporta la disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="7448e-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="7448e-108">Se è necessaria un'etichetta che esegue il wrapping su più righe, è possibile annidare un altro elemento che supporta la disposizione testo e inserirlo nell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="7448e-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="7448e-109">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.TextBlock> per creare un'etichetta che esegue il wrapping di più righe di testo.</span><span class="sxs-lookup"><span data-stu-id="7448e-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="7448e-110">**Aggiungere un tasto di scelta e una disposizione testo all'etichetta**</span><span class="sxs-lookup"><span data-stu-id="7448e-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="7448e-111">Se è necessario un <xref:System.Windows.Controls.Label> che dispone di una chiave di accesso (tasto di scelta), usare il <xref:System.Windows.Controls.AccessText> elemento che si trova all'interno di <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="7448e-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="7448e-112">I controlli quali <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, e <xref:System.Windows.Controls.GroupBox> hanno modelli di controllo predefinito.</span><span class="sxs-lookup"><span data-stu-id="7448e-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="7448e-113">Questi modelli contengono un <xref:System.Windows.Controls.ContentPresenter>.</span><span class="sxs-lookup"><span data-stu-id="7448e-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="7448e-114">Una delle proprietà che è possibile impostare per il <xref:System.Windows.Controls.ContentPresenter> è <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", che è possibile usare per specificare una chiave di accesso per il controllo.</span><span class="sxs-lookup"><span data-stu-id="7448e-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="7448e-115">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Label> che dispone di una chiave di accesso e supporta la disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="7448e-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="7448e-116">Per abilitare la disposizione del testo, nell'esempio viene impostata la <xref:System.Windows.Controls.AccessText.TextWrapping%2A> proprietà e viene utilizzato un carattere di sottolineatura per specificare la chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="7448e-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="7448e-117">Il carattere immediatamente successivo al carattere di sottolineatura è il tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="7448e-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="7448e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7448e-118">See also</span></span>
- [<span data-ttu-id="7448e-119">Procedura: Impostare la proprietà di destinazione di un'etichetta</span><span class="sxs-lookup"><span data-stu-id="7448e-119">How to: Set the Target Property of a Label</span></span>](https://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
