---
title: 'Procedura: Ereditare dalla classe UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7f4055c2374103b7df941d9a9bef24ed5e6cb27c
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015834"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Procedura: Ereditare dalla classe UserControl

Per combinare le funzionalità di uno o più controlli Windows Form con il codice personalizzato, è possibile creare un *controllo utente*. I controlli utente combinano lo sviluppo rapido del controllo, la funzionalità del controllo standard di Windows Forms e la versatilità di proprietà e metodi personalizzati. Quando si inizia con la creazione di un controllo utente, viene visualizzata una finestra di progettazione in cui è possibile inserire controlli Windows Forms standard. Questi controlli mantengono tutte le funzionalità intrinseche, nonché l'aspetto e il comportamento dei controlli standard. Una volta che questi controlli sono incorporati nel controllo utente, tuttavia, non sono più disponibili tramite codice. Il controllo utente esegue il proprio disegno e gestisce anche tutte le funzionalità di base associate ai controlli.

## <a name="to-create-a-user-control"></a>Per creare un controllo utente

1. Creare un nuovo progetto di **libreria di controlli Windows** in Visual Studio.

   Viene creato un nuovo progetto con un controllo utente vuoto.

2. Trascinare i controlli dalla scheda **Windows Forms** della **Casella degli strumenti** nella finestra di progettazione.

3. Questi controlli devono essere posizionati e progettati come si desidera che vengano visualizzati nel controllo utente finale. Se si desidera consentire agli sviluppatori di accedere ai controlli costitutivi, è necessario dichiararli come public o esporre in modo selettivo le proprietà del controllo che li costituiscono. Per informazioni dettagliate, vedere [Procedura: Esporre le proprietà dei controlli](how-to-expose-properties-of-constituent-controls.md)costitutivi.

4. Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.

5. Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.

## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)
- [Procedura: Ereditare da controlli Windows Forms esistenti](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedura: Controlli autore per Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Risolvere i problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Procedura: Testare il comportamento in fase di esecuzione di un UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
