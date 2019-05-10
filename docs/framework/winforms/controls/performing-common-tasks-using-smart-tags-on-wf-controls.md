---
title: 'Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211411"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form

Come si costruisce form e controlli per l'applicazione Windows Forms, esistono molte attività che verranno eseguite più volte. Queste sono alcune delle attività comuni eseguite che si verifica:

- Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.

- Ancoraggio di un controllo all'elemento padre.

- Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.

Per velocizzare lo sviluppo, molti controlli dispongono di smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni, ad esempio in una singola operazione in fase di progettazione. Queste attività vengono chiamate *smart tag verbi*.

Gli smart tag resta collegato a un'istanza di controllo per la relativa durata nella finestra di progettazione e sono sempre disponibili.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione di un progetto Windows Form

- Usando gli smart tag

- Abilitazione e disabilitazione degli Smart tag

Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.

## <a name="create-the-project"></a>Creare il progetto

Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.

1. In Visual Studio, creare un progetto di applicazione basata su Windows denominato "SmartTagsExample" (**File** > **New** > **progetto**  >  **Visual C#**  oppure **Visual Basic** > **Desktop classico** > **Windows Form Applicazione**).

2. Selezionare il form nel **finestra di progettazione Windows Form**.

## <a name="use-smart-tags"></a>Usare gli smart tag

Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che sono disponibili.

1. Trascinare un <xref:System.Windows.Forms.TabControl> dal **casella degli strumenti** nel form. Si noti il glifo smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) che viene visualizzato sul lato del <xref:System.Windows.Forms.TabControl>.

2. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **Aggiungi scheda** elemento. Si osservi che viene aggiunta una nuova pagina della scheda per il <xref:System.Windows.Forms.TabControl>.

3. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

4. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **Aggiungi colonna** elemento. Si osservi che viene aggiunta una nuova colonna per il <xref:System.Windows.Forms.TableLayoutPanel> controllo.

5. Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.

6. Fare clic sul glifo dello smart tag. Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **orientamento divisione orizzontale** elemento. Si noti che il <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è ora orientamento orizzontale.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [Procedura dettagliata: Aggiunta di Smart tag per un componente di Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))
