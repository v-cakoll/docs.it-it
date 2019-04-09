---
title: 'Procedura: Creare un controllo con un tasto di scelta e la disposizione testo'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 48e439719afa2426b5d8f822c621080cdc32514e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174044"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="597ff-102">Procedura: Creare un controllo con un tasto di scelta e la disposizione testo</span><span class="sxs-lookup"><span data-stu-id="597ff-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="597ff-103">Questo esempio illustra come creare un controllo dotato di un tasto di scelta e con un supporto di disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="597ff-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="597ff-104">Nell'esempio viene usato un <xref:System.Windows.Controls.Label> controllo per illustrare questi concetti.</span><span class="sxs-lookup"><span data-stu-id="597ff-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="597ff-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="597ff-105">Example</span></span>  
 **<span data-ttu-id="597ff-106">Aggiungere la disposizione del testo all'etichetta</span><span class="sxs-lookup"><span data-stu-id="597ff-106">Add Text Wrapping to Your Label</span></span>**  
  
 <span data-ttu-id="597ff-107">Il <xref:System.Windows.Controls.Label> controllo non supporta la disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="597ff-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="597ff-108">Se è necessaria un'etichetta che esegue il wrapping su più righe, è possibile annidare un altro elemento che supporta la disposizione testo e inserirlo nell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="597ff-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="597ff-109">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.TextBlock> per creare un'etichetta che esegue il wrapping di più righe di testo.</span><span class="sxs-lookup"><span data-stu-id="597ff-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **<span data-ttu-id="597ff-110">Aggiungere una chiave di accesso e la disposizione testo all'etichetta</span><span class="sxs-lookup"><span data-stu-id="597ff-110">Add an Access Key and Text Wrapping to Your Label</span></span>**  
  
 <span data-ttu-id="597ff-111">Se è necessario un <xref:System.Windows.Controls.Label> che dispone di una chiave di accesso (tasto di scelta), usare il <xref:System.Windows.Controls.AccessText> elemento che si trova all'interno di <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="597ff-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="597ff-112">I controlli quali <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, e <xref:System.Windows.Controls.GroupBox> hanno modelli di controllo predefinito.</span><span class="sxs-lookup"><span data-stu-id="597ff-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="597ff-113">Questi modelli contengono un <xref:System.Windows.Controls.ContentPresenter>.</span><span class="sxs-lookup"><span data-stu-id="597ff-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="597ff-114">Una delle proprietà che è possibile impostare per il <xref:System.Windows.Controls.ContentPresenter> è <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", che è possibile usare per specificare una chiave di accesso per il controllo.</span><span class="sxs-lookup"><span data-stu-id="597ff-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="597ff-115">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Label> che dispone di una chiave di accesso e supporta la disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="597ff-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="597ff-116">Per abilitare la disposizione del testo, nell'esempio viene impostata la <xref:System.Windows.Controls.AccessText.TextWrapping%2A> proprietà e viene utilizzato un carattere di sottolineatura per specificare la chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="597ff-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="597ff-117">Il carattere immediatamente successivo al carattere di sottolineatura è il tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="597ff-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="597ff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="597ff-118">See also</span></span>

- [<span data-ttu-id="597ff-119">Procedura: Impostare la proprietà di destinazione di un'etichetta</span><span class="sxs-lookup"><span data-stu-id="597ff-119">How to: Set the Target Property of a Label</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))
