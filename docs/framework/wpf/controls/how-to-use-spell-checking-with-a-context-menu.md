---
title: 'Procedura: utilizzare il controllo ortografico con un menu di scelta rapida'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 257f343a7fa01e251159797a83e89b533292b6b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="a4581-102">Procedura: utilizzare il controllo ortografico con un menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="a4581-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="a4581-103">Per impostazione predefinita, quando si abilita il controllo ortografico in un controllo di modifica come <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, si ottengono le opzioni di controllo ortografico nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a4581-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="a4581-104">Ad esempio, quando gli utenti fare doppio clic su una parola, ricevono una serie di correzioni ortografiche suggerite o l'opzione per **Ignora tutto**.</span><span class="sxs-lookup"><span data-stu-id="a4581-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="a4581-105">Tuttavia, quando si esegue l'override di menu di scelta rapida predefinito con un menu di scelta rapida personalizzato, questa funzionalità viene persa ed è necessario scrivere codice per riabilitare la funzionalità di controllo ortografico nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a4581-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="a4581-106">Nell'esempio seguente viene illustrato come abilitare questa funzionalità in un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4581-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4581-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4581-107">Example</span></span>  
 <span data-ttu-id="a4581-108">Nell'esempio seguente il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che crea un <xref:System.Windows.Controls.TextBox> con alcuni eventi che vengono utilizzati per implementare il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a4581-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="a4581-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4581-109">Example</span></span>  
 <span data-ttu-id="a4581-110">Nell'esempio seguente viene illustrato il codice che implementa il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a4581-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="a4581-111">Il codice utilizzato per raggiungere questo obiettivo con un <xref:System.Windows.Controls.RichTextBox> è simile.</span><span class="sxs-lookup"><span data-stu-id="a4581-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="a4581-112">La differenza principale è nel passato al parametro di `GetSpellingError` metodo.</span><span class="sxs-lookup"><span data-stu-id="a4581-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="a4581-113">Per un <xref:System.Windows.Controls.TextBox>, passare l'indice integer della posizione del punto di inserimento:</span><span class="sxs-lookup"><span data-stu-id="a4581-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="a4581-114">Per un <xref:System.Windows.Controls.RichTextBox>, passare il <xref:System.Windows.Documents.TextPointer> che specifica la posizione del cursore:</span><span class="sxs-lookup"><span data-stu-id="a4581-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="a4581-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4581-115">See Also</span></span>  
 [<span data-ttu-id="a4581-116">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="a4581-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="a4581-117">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a4581-117">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="a4581-118">Attivare il controllo ortografico in un controllo di modifica del testo</span><span class="sxs-lookup"><span data-stu-id="a4581-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [<span data-ttu-id="a4581-119">Usare un menu di scelta rapida personalizzato con un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="a4581-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
