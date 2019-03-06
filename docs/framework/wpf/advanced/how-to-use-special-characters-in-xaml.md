---
title: 'Procedura: Utilizzare caratteri speciali in XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 18934e06f45ca4b88f48bce8a310a07b460a5f53
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377963"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Procedura: Utilizzare caratteri speciali in XAML
I file di markup che vengono creati nella [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] vengono salvati automaticamente nel [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato di file UTF-8, il che significa che i caratteri speciali, ad esempio gli accenti, vengono codificate correttamente. Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente. Questi caratteri speciali seguono il [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard per la codifica.  
  
 La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:  
  
|Carattere|Sintassi|Descrizione|  
|---------------|------------|-----------------|  
|<|`&lt;`|Simbolo minore di.|  
|>|`&gt;`|Simbolo maggiore di.|  
|&|`&amp;`|Simbolo e commerciale.|  
|"|`&quot;`|Simbolo virgoletta doppia.|  
  
> [!NOTE]
>  Se si crea un file di markup usando un testo dell'editor, ad esempio [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] blocco note, è necessario salvare il file nei [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato di file UTF-8 per mantenere i caratteri speciali codificati.  
  
 L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
