---
title: Sicurezza dei controlli WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095255"
---
# <a name="webbrowser-security"></a>Sicurezza dei controlli WebBrowser
Il controllo <xref:System.Windows.Forms.WebBrowser> è progettato per funzionare solo con attendibilità totale. Il contenuto HTML visualizzato nel controllo può provenire da server Web esterni e può contenere codice non gestito sotto forma di script o controlli Web. Se si utilizza il controllo <xref:System.Windows.Forms.WebBrowser> in questa situazione, il controllo non è meno sicuro di Internet Explorer, ma il controllo <xref:System.Windows.Forms.WebBrowser> gestito non impedisce l'esecuzione di tale codice non gestito.  
  
 Per ulteriori informazioni sui problemi di sicurezza relativi al controllo `WebBrowser` ActiveX sottostante, vedere [controllo WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- [Panoramica sul controllo WebBrowser](webbrowser-control-overview.md)
- [Controllo WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
