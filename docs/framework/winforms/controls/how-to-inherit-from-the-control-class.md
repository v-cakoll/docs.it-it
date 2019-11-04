---
title: 'Procedura: ereditare dalla classe Control'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458378"
---
# <a name="how-to-inherit-from-the-control-class"></a>Procedura: ereditare dalla classe Control

Se si vuole creare un controllo completamente personalizzato da usare in un Windows Form, è necessario ereditare dalla classe <xref:System.Windows.Forms.Control>. Mentre l'ereditarietà dalla classe <xref:System.Windows.Forms.Control> richiede l'esecuzione di una maggiore pianificazione e implementazione, offre anche la più ampia gamma di opzioni. Quando si eredita da <xref:System.Windows.Forms.Control>, si ereditano le funzionalità di base che rendono i controlli funzionanti. La funzionalità inerente alla classe <xref:System.Windows.Forms.Control> gestisce l'input dell'utente attraverso la tastiera e il mouse, definisce i limiti e le dimensioni del controllo, fornisce un handle di Windows e fornisce la gestione e la sicurezza dei messaggi. Non incorpora nessun disegno, che in questo caso è il rendering reale dell'interfaccia grafica del controllo, e non consente di incorporare alcuna funzionalità di interazione utente specifica. È necessario fornire tutti questi aspetti tramite codice personalizzato.

## <a name="to-create-a-custom-control"></a>Per creare un controllo personalizzato

1. In Visual Studio creare una nuova **applicazione Windows** o un progetto **libreria di controlli Windows** .

2. Scegliere **Aggiungi classe** dal menu **Progetto**.

3. Nella finestra di dialogo **Aggiungi nuovo elemento**, fare clic su **Controllo personalizzato**.

   Un nuovo controllo personalizzato viene aggiunto al progetto.

4. Premere **F7** per aprire l' **editor di codice** per il controllo personalizzato.

5. Individuare il metodo <xref:System.Windows.Forms.Control.OnPaint%2A>, che sarà vuoto ad eccezione di una chiamata al metodo <xref:System.Windows.Forms.Control.OnPaint%2A> della classe di base.

6. Modificare il codice per incorporare il disegno personalizzato desiderato per il controllo.

   Per informazioni sul codice di scrittura per eseguire il rendering della grafica dei controlli, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).

7. Implementare eventuali metodi, proprietà o eventi personalizzati da incorporare nel controllo.

8. Salvare ed eseguire il test del controllo.

## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Ereditare da controlli Windows Form esistenti](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedura: Creare controlli per Windows Form](how-to-author-controls-for-windows-forms.md)
- [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
