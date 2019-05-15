---
title: "Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog"
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: f2fb48e07243694b14904b240bdcb0739175c2fc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593535"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog
È possibile risolvere i problemi di interoperabilità modello COM (Component Object), visualizzare il Form di Windows in un ciclo di messaggi di .NET Framework, che viene creato utilizzando il <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> (metodo).  
  
 Per fare in modo che un form funzioni correttamente da un'applicazione client COM, è necessario eseguirlo in un ciclo di messaggi Windows Form. Per eseguire questa operazione, adottare uno degli approcci seguenti:  
  
- Usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il Windows Form.  
  
- Visualizzare ogni Windows Form in un thread separato. Per altre informazioni, vedere [Procedura: Supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Routine  
 Uso di <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> metodo può essere il modo più semplice per visualizzare un form in un ciclo di messaggi di .NET Framework, poiché, di tutti gli approcci, richiede il minor quantità di codice per implementare.  
  
 Il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> sospende il ciclo di messaggi dell'applicazione non gestita e visualizza il form come una finestra di dialogo. Poiché il ciclo di messaggi dell'applicazione host è stato sospeso, il <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> metodo crea un nuovo ciclo di messaggi di .NET Framework per elaborare i messaggi del form.  
  
 Lo svantaggio dell'uso del metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> consiste nel fatto che il form viene aperto come finestra di dialogo modale. Questo comportamento blocca eventuali interfacce utente (UI) nell'applicazione chiamante mentre il Windows Form è aperto. Quando l'utente chiude il form, chiude il ciclo di messaggi di .NET Framework e il ciclo di messaggi dell'applicazione precedente viene eseguito di nuovo.  
  
 È possibile creare una libreria di classi in Windows Form che dispone di un metodo per visualizzare il form e quindi compilare la libreria di classi per l'interoperabilità COM. È possibile usare questo file DLL da Visual Basic 6.0 o Microsoft Foundation Classes (MFC) e da uno dei due ambienti è possibile chiamare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il form.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Per supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog  
  
- Sostituire tutte le chiamate per il <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> con le chiamate al metodo il <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> metodo all'interno del componente di .NET Framework.  
  
## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti .NET Framework a COM](../../interop/exposing-dotnet-components-to-com.md)
- [Procedura: Supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Form e applicazioni non gestite](windows-forms-and-unmanaged-applications.md)
