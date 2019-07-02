---
title: Cenni preliminari sulla grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505329"
---
# <a name="overview-of-graphics"></a>Cenni preliminari sulla grafica
GDI+ è un'application programming interface (API) che costituisce il sottosistema del sistema operativo Microsoft Windows. GDI+ è responsabile della visualizzazione di informazioni sugli schermi e stampanti. Come suggerisce il nome, GDI+ è il successore di GDI, Graphics Device Interface incluse nelle versioni precedenti di Windows.  
  
## <a name="managed-class-interface"></a>Interfaccia di classe gestita  
 L'API di GDI+ vengono esposti tramite un set di classi distribuito come codice gestito. Questo set di classi viene chiamato il *interfaccia di classe gestita* per GDI+. Di seguito sono elencati gli spazi dei nomi che costituiscono l'interfaccia di classe gestita:  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 Con una Graphics Device Interface, ad esempio GDI+, è possibile visualizzare informazioni su un monitor o una stampante senza doversi preoccupare dei dettagli relativi a un dispositivo di visualizzazione particolare. Il programmatore effettua chiamate ai metodi forniti dalle classi di GDI+. Tali metodi, a loro volta, effettuano le chiamate appropriate a specifici driver di dispositivo. GDI+ isola l'applicazione dall'hardware grafico. È questo isolamento che consente a un programmatore di creare applicazioni indipendenti dal dispositivo.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla grafica](graphics-overview-windows-forms.md)
