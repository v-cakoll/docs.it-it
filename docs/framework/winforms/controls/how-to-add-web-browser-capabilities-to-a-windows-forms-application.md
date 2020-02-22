---
title: Aggiungere funzionalità del browser Web all'app
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: 7cb789121f4aa9a1e7cef54f992d0697ce6dfc62
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543573"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a>Come aggiungere funzionalità del browser Web a un Windows Forms Application

Il controllo <xref:System.Windows.Forms.WebBrowser> consente di aggiungere funzionalità del Web browser all'applicazione. Per impostazione predefinita, il controllo funziona come un Web browser. Dopo aver caricato un URL iniziale mediante l'impostazione della proprietà <xref:System.Windows.Forms.WebBrowser.Url%2A>, è possibile fare clic sui collegamenti ipertestuali o usare i tasti di scelta rapida per muoversi in avanti o all'indietro nella cronologia di spostamento. Per impostazione predefinita, è possibile accedere ad altre funzionalità del browser mediante il menu di scelta rapida. È anche possibile aprire nuovi documenti trascinandoli e rilasciandoli sul controllo. Il controllo <xref:System.Windows.Forms.WebBrowser> dispone anche di numerose proprietà, metodi ed eventi che possono essere usati per implementare funzionalità dell'interfaccia utente simili a quelle disponibili in Internet Explorer.

Nell'esempio di codice seguente vengono implementati una barra degli indirizzi, i tipici pulsanti del browser, un menu **File**, una barra di stato e una barra del titolo contenente il titolo della pagina corrente.

## <a name="example"></a>Esempio

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a>Compilare il codice

L'esempio presenta i requisiti seguenti:

- Riferimenti agli assembly `System`, `System.Drawing` e `System.Windows.Forms`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- [Controllo WebBrowser](webbrowser-control-windows-forms.md)
