---
title: 'Procedura: Creare form padre MDI'
description: Informazioni su come creare un form padre MDI a livello di codice e usando il Progettazione Windows Form.
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: d387837a565ca247f62828c19f353990b35117c7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174705"
---
# <a name="how-to-create-mdi-parent-forms"></a>Procedura: Creare form padre MDI

> [!IMPORTANT]
> In questo argomento viene usato il controllo <xref:System.Windows.Forms.MainMenu> che è stato sostituito dal controllo <xref:System.Windows.Forms.MenuStrip>. Il controllo <xref:System.Windows.Forms.MainMenu> viene mantenuto per la compatibilità con le versioni precedenti e per l'uso futuro, se si desidera. Per informazioni sulla creazione di un form padre MDI usando un <xref:System.Windows.Forms.MenuStrip> , vedere [procedura: creare un elenco di finestre MDI con MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).

La base di un'applicazione MDI (interfaccia a documenti multipli, Multiple Document Interface) è il form padre MDI. Si tratta del form che contiene le finestre figlio MDI che rappresentano le sottofinestre in cui l'utente interagisce con l'applicazione MDI. La creazione di un form padre MDI è semplice sia in Progettazione Windows Form che a livello di codice.

## <a name="create-an-mdi-parent-form-at-design-time"></a>Creazione di un form padre MDI in fase di progettazione

1. Creare un progetto di applicazione Windows in Visual Studio.

2. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà su **true**.

     Il form viene così designato come contenitore MDI per le finestre figlio.

    > [!NOTE]
    > Quando si impostano le proprietà nella finestra **Proprietà**, se si vuole è anche possibile impostare la proprietà `WindowState` su **Ingrandita** per semplificare la modifica delle finestre figlio MDI ingrandendo il form padre. Inoltre, tenere presente che il bordo del form padre MDI applica il colore del sistema (impostato nel Pannello di controllo del sistema Windows) e non il colore di sfondo impostato con la proprietà <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.

3. Dalla **Casella degli strumenti** trascinare un controllo **MenuStrip** nel form. Creare una voce di menu di primo livello con la proprietà **Testo** impostata su **&File** con voci di sottomenu chiamate **&Nuovo** e **&Chiudi**. Creare anche una voce di menu di primo livello chiamata **&Finestra**.

     Il primo menu crea e nasconde le voci di menu al runtime, mentre il secondo tiene traccia delle finestre figlio MDI aperte. A questo punto è stata creata una finestra padre MDI.

4. Premere **F5** per eseguire l'applicazione. Per informazioni sulla creazione di finestre figlio MDI usate all'interno del form padre MDI, vedere [Procedura: Creare form figlio MDI](how-to-create-mdi-child-forms.md).

## <a name="see-also"></a>Vedere anche

- [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](multiple-document-interface-mdi-applications.md)
- [Procedura: creare form figlio MDI](how-to-create-mdi-child-forms.md)
- [Procedura: determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md)
- [Procedura: inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)
- [Procedura: Disporre i form figlio MDI](how-to-arrange-mdi-child-forms.md)
