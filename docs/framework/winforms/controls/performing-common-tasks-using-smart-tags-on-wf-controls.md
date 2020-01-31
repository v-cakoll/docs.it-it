---
title: Eseguire attività comuni usando gli smart tag nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744264"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>Procedura dettagliata: eseguire attività comuni usando gli smart tag

Quando si costruiscono moduli e controlli per la Windows Forms Application, è possibile eseguire ripetutamente diverse attività. Di seguito sono riportate alcune delle attività comunemente eseguite che si verificheranno:

- Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.

- Ancoraggio di un controllo al relativo elemento padre.

- Modifica dell'orientamento di un controllo <xref:System.Windows.Forms.SplitContainer>.

Per velocizzare lo sviluppo, molti controlli offrono smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni come queste in un singolo gesto in fase di progettazione. Queste attività sono denominate *verbi smart tag*.

Gli smart tag rimangono collegati a un'istanza del controllo per la sua durata nella finestra di progettazione e sono sempre disponibili.

## <a name="create-the-project"></a>Creare il progetto

Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato **SmartTagsExample**.

2. Selezionare il modulo nella **Progettazione Windows Form**.

## <a name="use-smart-tags"></a>Usa Smart Tag

Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che li offrono.

1. Trascinare un <xref:System.Windows.Forms.TabControl> dalla **casella degli strumenti** nel form. Si noti il glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif)) che viene visualizzato sul lato della <xref:System.Windows.Forms.TabControl>.

2. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida visualizzato accanto al glifo selezionare la voce **Aggiungi scheda** . Osservare che alla <xref:System.Windows.Forms.TabControl>viene aggiunta una nuova scheda.

3. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

4. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento **Aggiungi colonna** . Osservare che una nuova colonna viene aggiunta al controllo <xref:System.Windows.Forms.TableLayoutPanel>.

5. Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.

6. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento di **orientamento della barra di divisione orizzontale** . Osservare che la barra di divisione del controllo <xref:System.Windows.Forms.SplitContainer> è ora orientata orizzontalmente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
