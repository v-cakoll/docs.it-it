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
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526453"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Suggerimenti per il controllo TableLayoutPanel
Il <xref:System.Windows.Forms.TableLayoutPanel> controllo fornisce potenti funzioni di layout che è necessario considerare con attenzione prima di usare in Windows Form.  
  
## <a name="recommendations"></a>Suggerimenti  
 I suggerimenti seguenti consentono di utilizzare il <xref:System.Windows.Forms.TableLayoutPanel> controllo relativo ottimale.  
  
### <a name="targeted-use"></a>Utilizzo di destinazione  
 Utilizzare il <xref:System.Windows.Forms.TableLayoutPanel> controllare con cautela. È consigliabile non utilizzare in tutte le situazioni che richiedono un layout ridimensionabile. Nell'elenco seguente vengono descritti i layout che traggono dall'utilizzo del <xref:System.Windows.Forms.TableLayoutPanel> controllo:  
  
-   Layout in cui sono presenti più parti del form di ridimensionare in modo proporzionale a altro.  
  
-   Layout che verrà generato in modo dinamico in fase di esecuzione, ad esempio moduli di immissione dati che dispongono di campi personalizzabili aggiunte o sottratte o modificati in base alle preferenze.  
  
-   Layout che deve rimanere in una dimensione fissa globale. Ad esempio, potrebbe essere una finestra di dialogo che deve rimanere inferiore a 800 x 600, ma è necessario supportare le stringhe localizzate.  
  
 Nell'elenco seguente vengono descritti i layout che non traggono dall'utilizzo di <xref:System.Windows.Forms.TableLayoutPanel> controllo:  
  
-   Semplice moduli di immissione dati con una singola colonna di etichette e una singola colonna di aree di immissione di testo.  
  
-   Form con un unico grande Visualizza l'area che deve occupare tutto lo spazio disponibile quando si verifica un ridimensionamento. Un esempio di questo è un modulo che consente di visualizzare un singolo <xref:System.Windows.Forms.PropertyGrid> controllo. In questo caso, utilizzare l'ancoraggio perché nessun altro elemento deve espandere quando il form viene ridimensionato.  
  
 Scegliere con attenzione i controlli che devono essere un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Se si dispone di spazio per il testo per l'aumento delle dimensioni del 30% tramite ancoraggio, è consigliabile utilizzare il <xref:System.Windows.Forms.Control.Anchor%2A> solo per la proprietà. Se è possibile stimare lo spazio richiesto dal layout, consente di <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> anziché stimare i dettagli dello spazio rimanente e <xref:System.Windows.Forms.Control.AutoSize%2A> comportamento.  
  
 In generale, quando si progetta il layout con il <xref:System.Windows.Forms.TableLayoutPanel> di controllo, semplificare la progettazione.  
  
### <a name="use-the-document-outline-window"></a>Utilizzare la finestra Struttura documento  
 La finestra Struttura documento offre una visualizzazione albero di layout, che è possibile utilizzare per modificare le relazioni padre-figlio e di ordine z dei controlli. Dal **dal menu Visualizza**selezionare **altre finestre**, quindi selezionare **struttura documento**.  
  
### <a name="avoid-nesting"></a>Evitare l'annidamento  
 Evitare di annidare altri <xref:System.Windows.Forms.TableLayoutPanel> controlli all'interno di un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Può essere difficile il debug di layout nidificati.  
  
### <a name="avoid-visual-inheritance"></a>Evitare l'ereditarietà visiva  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo non supporta l'ereditarietà visiva in Progettazione Windows Form. Oggetto <xref:System.Windows.Forms.TableLayoutPanel> come "bloccato" in fase di progettazione verrà visualizzato un controllo in una classe derivata.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
