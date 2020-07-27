---
title: Supportare pattern di controllo in un provider di automazione interfaccia utente
description: Informazioni su come implementare i pattern di controllo di supporto in un provider di automazione interfaccia utente in modo che le applicazioni client possano modificare i controlli e ottenere dati da essi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 82300499520be6b820b361ebdeb56bbf3716afab
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163506"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a>Supportare pattern di controllo in un provider di automazione interfaccia utente

> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).

In questo argomento viene descritto come implementare uno o più pattern di controllo in un provider di automazione interfaccia utente in modo che le applicazioni client possano modificare i controlli e ottenere dati.

## <a name="support-control-patterns"></a>Supportare i pattern di controllo

1. Implementare le interfacce appropriate per i pattern di controllo che l'elemento deve supportare, ad esempio <xref:System.Windows.Automation.Provider.IInvokeProvider> per <xref:System.Windows.Automation.InvokePattern>.

2. Restituire l'oggetto che contiene l'implementazione di ciascuna interfaccia di controllo nell'implementazione di <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType>

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata un'implementazione di <xref:System.Windows.Automation.Provider.ISelectionProvider> per una casella di riepilogo personalizzata a selezione singola. Restituisce tre proprietà e ottiene l'elemento attualmente selezionato.

[!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
[!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata un'implementazione <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> che restituisce la classe che implementa <xref:System.Windows.Automation.Provider.ISelectionProvider>. La maggior parte dei controlli casella di riepilogo supporta anche altri pattern, ma in questo esempio viene restituito un riferimento null ( `Nothing` in Microsoft Visual Basic .NET) per tutti gli altri identificatori di criteri.

[!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
[!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui provider di automazione interfaccia utente](ui-automation-providers-overview.md)
- [Implementazione del provider di automazione interfaccia utente lato server](server-side-ui-automation-provider-implementation.md)
