---
title: 'Procedura: Usare caratteri speciali in XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 308b2152f98286ba532a15e5491b5d1a25aa66dd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="ac223-102">Procedura: Usare caratteri speciali in XAML</span><span class="sxs-lookup"><span data-stu-id="ac223-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="ac223-103">File di markup che vengono creati in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] vengono salvate automaticamente nel [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato di file UTF-8, il che significa che i caratteri speciali, ad esempio accenti, vengono codificati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac223-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="ac223-104">Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente.</span><span class="sxs-lookup"><span data-stu-id="ac223-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="ac223-105">Seguono questi caratteri speciali di [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard per la codifica.</span><span class="sxs-lookup"><span data-stu-id="ac223-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="ac223-106">La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="ac223-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="ac223-107">Carattere</span><span class="sxs-lookup"><span data-stu-id="ac223-107">Character</span></span>|<span data-ttu-id="ac223-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac223-108">Syntax</span></span>|<span data-ttu-id="ac223-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac223-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`<`|<span data-ttu-id="ac223-110">Simbolo minore di.</span><span class="sxs-lookup"><span data-stu-id="ac223-110">Less than symbol.</span></span>|  
|>|`>`|<span data-ttu-id="ac223-111">Simbolo maggiore di.</span><span class="sxs-lookup"><span data-stu-id="ac223-111">Greater than sign.</span></span>|  
|&|`&`|<span data-ttu-id="ac223-112">Simbolo e commerciale.</span><span class="sxs-lookup"><span data-stu-id="ac223-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="ac223-113">"</span><span class="sxs-lookup"><span data-stu-id="ac223-113">"</span></span>|`"`|<span data-ttu-id="ac223-114">Simbolo virgoletta doppia.</span><span class="sxs-lookup"><span data-stu-id="ac223-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ac223-115">Se si crea un file di markup mediante un testo dell'editor, ad esempio [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] blocco note, è necessario salvare il file di [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] il formato di file UTF-8 per mantenere qualsiasi codifica i caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="ac223-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="ac223-116">L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.</span><span class="sxs-lookup"><span data-stu-id="ac223-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac223-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac223-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
