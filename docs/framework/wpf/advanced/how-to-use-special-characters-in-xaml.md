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
ms.openlocfilehash: 27f2b18593d075b54eb8c3351bbb84415700cfd4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395797"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Procedura: Usare caratteri speciali in XAML
I file di markup creati in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] vengono salvati automaticamente nel formato di file UTF-8 Unicode, il che significa che la maggior parte dei caratteri speciali, ad esempio i contrassegni accentati, sono codificati correttamente. Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente. Questi caratteri speciali seguono lo standard [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] per la codifica.  
  
 La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:  
  
|Carattere|Sintassi|Descrizione|  
|---------------|------------|-----------------|  
|<|`&lt;`|Simbolo minore di.|  
|>|`&gt;`|Simbolo maggiore di.|  
|&|`&amp;`|Simbolo e commerciale.|  
|"|`&quot;`|Simbolo virgoletta doppia.|  
  
> [!NOTE]
> Se si crea un file di markup usando un editor di testo, ad esempio Blocco note di Windows, è necessario salvare il file nel formato di file UTF-8 Unicode per mantenere i caratteri speciali codificati.  
  
 L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
