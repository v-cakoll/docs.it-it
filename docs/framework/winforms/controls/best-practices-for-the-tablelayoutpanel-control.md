---
title: Suggerimenti per il controllo TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 6be6d0904d5b52e5188f0a5a16aaefa08265379c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674193"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Suggerimenti per il controllo TableLayoutPanel
Il <xref:System.Windows.Forms.TableLayoutPanel> controllo fornisce funzionalità di layout avanzate che è opportuno considerare con attenzione prima di utilizzare nei Windows Form.  
  
## <a name="recommendations"></a>Suggerimenti  
 I suggerimenti seguenti consentiranno di usare il <xref:System.Windows.Forms.TableLayoutPanel> controllo a proprio vantaggio migliore.  
  
### <a name="targeted-use"></a>Uso specifici  
 Usare il <xref:System.Windows.Forms.TableLayoutPanel> controllare in modo sporadico. Non è necessario usarlo in tutte le situazioni che richiedono un layout ridimensionabile. Nell'elenco seguente vengono descritti i layout che traggono vantaggio dall'utilizzo di più il <xref:System.Windows.Forms.TableLayoutPanel> controllo:  
  
-   Layout in cui sono presenti più parti nel formato che ridimensionano in modo proporzionale tra loro.  
  
-   Layout che verranno generate dinamicamente in fase di esecuzione, ad esempio form di immissione di dati con campi personalizzabili dall'utente aggiunte o sottratte o modificato in base alle preferenze.  
  
-   Layout che deve rimanere in una dimensione fissa globale. Ad esempio, potrebbe essere una finestra di dialogo che deve rimanere inferiore a 800 x 600, ma è necessario supportare le stringhe localizzate.  
  
 Nell'elenco seguente vengono descritti i layout che non traggono notevoli vantaggi dall'utilizzo di <xref:System.Windows.Forms.TableLayoutPanel> controllo:  
  
-   Semplice moduli di immissione dati con una sola colonna di etichette e una singola colonna delle aree di immissione di testo.  
  
-   Form con un unico grande Visualizza area che deve occupare tutto lo spazio disponibile quando si verifica un ridimensionamento. Un esempio di questo oggetto è una forma che visualizza una singola <xref:System.Windows.Forms.PropertyGrid> controllo. In questo caso, utilizzare l'ancoraggio perché nessun altro elemento deve espandere quando il form viene ridimensionato.  
  
 Scegliere con attenzione i controlli che devono essere in un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Se si dispone di spazio per la crescita del 30% usando l'ancoraggio del testo, è consigliabile usare il <xref:System.Windows.Forms.Control.Anchor%2A> solo la proprietà. Se è possibile stimare lo spazio richiesto per il layout, usare <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> è più facile che stima i dettagli dello spazio rimanente e <xref:System.Windows.Forms.Control.AutoSize%2A> comportamento.  
  
 In generale, quando si progetta il layout con il <xref:System.Windows.Forms.TableLayoutPanel> controllare, semplificare la progettazione.  
  
### <a name="use-the-document-outline-window"></a>Utilizzare la finestra Struttura documento  
 La finestra Struttura documento offre una visualizzazione albero del layout, che è possibile usare per modificare le relazioni padre-figlio e ordine z dei controlli. Dal **dal menu**, selezionare **Other Windows**, quindi selezionare **struttura documento**.  
  
### <a name="avoid-nesting"></a>Evitare l'annidamento  
 Evitare l'annidamento altri <xref:System.Windows.Forms.TableLayoutPanel> controlli all'interno di un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Layout annidati di debug può essere difficile.  
  
### <a name="avoid-visual-inheritance"></a>Evitare ereditarietà visiva  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo non supporta l'ereditarietà visiva in Progettazione Windows Form. Oggetto <xref:System.Windows.Forms.TableLayoutPanel> controllo in una classe derivata viene visualizzato come "bloccato" in fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
