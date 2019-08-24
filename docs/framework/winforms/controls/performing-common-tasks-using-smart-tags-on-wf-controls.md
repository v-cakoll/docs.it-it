---
title: 'Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015755"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>Procedura dettagliata: Eseguire attività comuni usando gli smart tag

Quando si costruiscono moduli e controlli per la Windows Forms Application, è possibile eseguire ripetutamente diverse attività. Di seguito sono riportate alcune delle attività comunemente eseguite che si verificheranno:

- Aggiunta o rimozione di una scheda in <xref:System.Windows.Forms.TabControl>un oggetto.

- Ancoraggio di un controllo al relativo elemento padre.

- Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.

Per velocizzare lo sviluppo, molti controlli offrono smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni come queste in un singolo gesto in fase di progettazione. Queste attività sono denominate *verbi smart tag*.

Gli smart tag rimangono collegati a un'istanza del controllo per la sua durata nella finestra di progettazione e sono sempre disponibili.

## <a name="create-the-project"></a>Creare il progetto

Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato **SmartTagsExample**.

2. Selezionare il modulo nella **Progettazione Windows Form**.

## <a name="use-smart-tags"></a>Usa Smart Tag

Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che li offrono.

1. Trascinare un <xref:System.Windows.Forms.TabControl> oggetto dalla **casella degli strumenti** nel form. Si noti il glifo smart tag (![glifo](./media/vs-winformsmttagglyph.gif)smart tag) che viene visualizzato <xref:System.Windows.Forms.TabControl>sul lato della.

2. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida visualizzato accanto al glifo selezionare la voce **Aggiungi scheda** . Osservare che viene aggiunta una nuova scheda a <xref:System.Windows.Forms.TabControl>.

3. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

4. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento **Aggiungi colonna** . Osservare che una nuova colonna viene aggiunta al <xref:System.Windows.Forms.TableLayoutPanel> controllo.

5. Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.

6. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento di **orientamento della barra di divisione orizzontale** . Osservare che la <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è ora orientata orizzontalmente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
