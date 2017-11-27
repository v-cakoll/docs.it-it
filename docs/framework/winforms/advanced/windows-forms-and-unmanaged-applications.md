---
title: Windows Form e applicazioni non gestite
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8166ab6a69ce9a774e83e6dbc7278a41805f7a83
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows Form e applicazioni non gestite
Le applicazioni e i controlli Windows Forms possono interagire con le applicazioni non gestite, con alcune raccomandazioni. Nelle sezioni che seguono vengono descritti configurazioni e scenari supportati e non supportati dalle applicazioni e dai controlli Windows Forms.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica su Windows Form e applicazioni non gestite](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Fornisce informazioni generali su come usare e implementare i controlli Windows Form che funzionano con le applicazioni non gestite.  
  
 [Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Fornisce un esempio di codice che illustra come usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per l'esecuzione di un Windows Form in un'applicazione non gestita.  
  
 [Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Fornisce un esempio di codice che illustra come eseguire un Windows Form nel relativo thread.  
  
 Vedere anche [Procedura dettagliata: supporto dell'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Usato per creare un thread separato per un Windows Form.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Avvia un ciclo di messaggi per un thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Effettua il marshalling di chiamate da un'applicazione non gestita a un form.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Esposizione di componenti .NET Framework a COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Fornisce informazioni generali sull'uso di tipi .NET Framework nelle applicazioni non gestite.
