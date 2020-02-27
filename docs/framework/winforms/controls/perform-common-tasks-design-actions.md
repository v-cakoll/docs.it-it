---
title: Eseguire attività comuni usando le azioni della finestra di progettazione sui controlli
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634883"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a>Procedura dettagliata: eseguire attività comuni utilizzando le azioni della finestra di progettazione

Quando si costruiscono moduli e controlli per la Windows Forms Application, le attività eseguite più volte sono numerose. Nell'elenco seguente vengono illustrate alcune delle attività comunemente eseguite:

- Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.
- Ancoraggio di un controllo al relativo elemento padre.
- Modifica dell'orientamento di un controllo <xref:System.Windows.Forms.SplitContainer>.

Per velocizzare lo sviluppo, molti controlli offrono azioni di progettazione, che sono menu sensibili al contesto che consentono di eseguire attività comuni come queste in un singolo gesto in fase di progettazione. Queste attività sono denominate *verbi di azioni della finestra di progettazione*.

Le azioni della finestra di progettazione rimangono associate a un'istanza del controllo per la sua durata nella finestra di progettazione e sono sempre disponibili.

## <a name="create-the-project"></a>Creare il progetto

Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato **DesignerActionsExample**.

2. Selezionare il modulo nella **Progettazione Windows Form**.

## <a name="use-designer-actions"></a>Usare le azioni di progettazione

Le azioni della finestra di progettazione sono sempre disponibili in fase di progettazione nei controlli che li offrono.

1. Trascinare un <xref:System.Windows.Forms.TabControl> dalla **casella degli strumenti** nel form. Si noti il glifo delle azioni della finestra di progettazione (![piccola freccia nera](./media/designer-actions-glyph.gif)) che viene visualizzato sul lato della <xref:System.Windows.Forms.TabControl>.

2. Fare clic sul glifo azioni della finestra di progettazione. Nel menu di scelta rapida visualizzato accanto al glifo selezionare la voce **Aggiungi scheda** . Osservare che alla <xref:System.Windows.Forms.TabControl>viene aggiunta una nuova scheda.

3. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

4. Fare clic sul glifo azioni della finestra di progettazione. Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento **Aggiungi colonna** . Osservare che una nuova colonna viene aggiunta al controllo <xref:System.Windows.Forms.TableLayoutPanel>.

5. Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.

6. Fare clic sul glifo azioni della finestra di progettazione. Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento di **orientamento della barra di divisione orizzontale** . Osservare che la barra di divisione del controllo <xref:System.Windows.Forms.SplitContainer> è ora orientata orizzontalmente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
