---
title: App non gestite
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 17dc20653d1628dfd460a9891e1b0a21c0ebecbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746360"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows Form e applicazioni non gestite
Le applicazioni e i controlli Windows Form possono interagire con le applicazioni non gestite, con alcune raccomandazioni. Nelle sezioni che seguono vengono descritti configurazioni e scenari supportati e non supportati dalle applicazioni e dai controlli Windows Form.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica su Windows Form e applicazioni non gestite](windows-forms-and-unmanaged-applications-overview.md)  
 Fornisce informazioni generali su come usare e implementare i controlli Windows Form che funzionano con le applicazioni non gestite.  
  
 [Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md)  
 Fornisce un esempio di codice che illustra come usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per l'esecuzione di un Windows Form in un'applicazione non gestita.  
  
 [Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Fornisce un esempio di codice che illustra come eseguire un Windows Form nel relativo thread.  
  
 Vedere anche [Procedura dettagliata: supporto dell'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Usato per creare un thread separato per un Windows Form.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Avvia un ciclo di messaggi per un thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Effettua il marshalling di chiamate da un'applicazione non gestita a un form.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Esposizione di componenti .NET Framework a COM](../../interop/exposing-dotnet-components-to-com.md)  
 Fornisce informazioni generali sull'uso di tipi .NET Framework nelle applicazioni non gestite.
