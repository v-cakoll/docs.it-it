---
title: 'Procedura: Usare caratteri speciali in XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918440"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="05343-102">Procedura: Usare caratteri speciali in XAML</span><span class="sxs-lookup"><span data-stu-id="05343-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="05343-103">I file di markup creati in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] vengono salvati automaticamente nel formato [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] di file UTF-8, il che significa che la maggior parte dei caratteri speciali, ad esempio i contrassegni accentati, sono codificati correttamente.</span><span class="sxs-lookup"><span data-stu-id="05343-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="05343-104">Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente.</span><span class="sxs-lookup"><span data-stu-id="05343-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="05343-105">Questi caratteri speciali seguono lo [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] standard per la [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] codifica.</span><span class="sxs-lookup"><span data-stu-id="05343-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="05343-106">La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="05343-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="05343-107">Carattere</span><span class="sxs-lookup"><span data-stu-id="05343-107">Character</span></span>|<span data-ttu-id="05343-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05343-108">Syntax</span></span>|<span data-ttu-id="05343-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05343-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="05343-110">Simbolo minore di.</span><span class="sxs-lookup"><span data-stu-id="05343-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="05343-111">Simbolo maggiore di.</span><span class="sxs-lookup"><span data-stu-id="05343-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="05343-112">Simbolo e commerciale.</span><span class="sxs-lookup"><span data-stu-id="05343-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="05343-113">"</span><span class="sxs-lookup"><span data-stu-id="05343-113">"</span></span>|`&quot;`|<span data-ttu-id="05343-114">Simbolo virgoletta doppia.</span><span class="sxs-lookup"><span data-stu-id="05343-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="05343-115">Se si crea un file di markup usando un editor di testo, ad esempio Blocco note di Windows, è necessario salvare [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] il file nel formato di file UTF-8 per mantenere i caratteri speciali codificati.</span><span class="sxs-lookup"><span data-stu-id="05343-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="05343-116">L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.</span><span class="sxs-lookup"><span data-stu-id="05343-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05343-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="05343-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
