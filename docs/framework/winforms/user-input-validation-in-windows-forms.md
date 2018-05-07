---
title: Convalida dell'input utente in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: adc138ad1e277f69f27f9f86fc5c3ea28a8d5cce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="user-input-validation-in-windows-forms"></a>Convalida dell'input utente in Windows Form
Quando gli utenti immettono i dati nell'applicazione, si desidera verificare che i dati siano validi prima di essere utilizzati nell'applicazione. Potrebbe essere necessario che alcuni campi di testo non sia di lunghezza zero, che un campo formattato come un numero di telefono o altro tipo di dati in formato corretto o che una stringa non contenga caratteri non sicuri che può essere usati per compromettere la sicurezza di un database. Windows Form sono disponibili diversi metodi per convalidare l'input dell'applicazione.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Convalida del controllo MaskedTextBox  
 Se è necessario richiedere agli utenti di immettere i dati in un formato ben definito, ad esempio un numero di telefono o un numero di parte, è possibile ottenere questo rapidamente e con minime al codice usando il <xref:System.Windows.Forms.MaskedTextBox> controllo. Oggetto *mask* è una stringa di caratteri da un linguaggio di maschera che specifica i caratteri che possono essere inseriti in qualsiasi posizione specificata nella casella di testo. Il controllo Visualizza una serie di richieste all'utente. Se l'utente digita una voce non valida, ad esempio, l'utente digita una lettera quando è richiesto un numero, il controllo Rifiuta automaticamente l'input.  
  
 La lingua di maschera che viene utilizzata da <xref:System.Windows.Forms.MaskedTextBox> è molto flessibile. Consente di specificare i caratteri richiesti, caratteri facoltativi, i caratteri letterali, ad esempio trattini e parentesi, valuta caratteri e separatori di Data. Il controllo funziona anche quando è associato a un'origine dati. Il <xref:System.Windows.Forms.Binding.Format> evento in un'associazione di dati può essere utilizzato per riformattare i dati in entrata per la conformità con la maschera e <xref:System.Windows.Forms.Binding.Parse> evento può essere utilizzato per riformattare i dati in uscita per rispettare le specifiche del campo dati.  
  
 Per ulteriori informazioni, vedere [controllo MaskedTextBox](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Convalida basata su eventi  
 Se si desidera un controllo a livello di codice completo sulla convalida o necessario eseguire controlli di convalida complessi, è necessario utilizzare gli eventi di convalida incorporati la maggior parte dei controlli Windows Form. Ogni controllo che accetta l'input dell'utente in formato libero dispone di un <xref:System.Windows.Forms.Control.Validating> evento che si verificherà ogni volta che il controllo richiede la convalida dei dati. Nel <xref:System.Windows.Forms.Control.Validating> il metodo di gestione degli eventi, è possibile convalidare l'input dell'utente in diversi modi. Ad esempio, se si dispone di una casella di testo che deve contenere un codice postale, è possibile eseguire la convalida nei modi seguenti:  
  
-   Se il codice postale deve appartenere a un gruppo specifico di codici postali, è possibile eseguire un confronto tra stringhe di input per convalidare i dati immessi dall'utente. Ad esempio, se il codice postale deve essere nel set {10001, 10002 10003}, è possibile utilizzare un confronto tra stringhe per convalidare i dati.  
  
-   Se il codice postale deve essere in un modulo specifico è possibile utilizzare espressioni regolari per convalidare i dati immessi dall'utente. Ad esempio, per convalidare il form `#####` o `#####-####`, è possibile utilizzare l'espressione regolare `^(\d{5})(-\d{4})?$`. Per convalidare il modulo `A#A #A#`, è possibile utilizzare l'espressione regolare `[A-Z]\d[A-Z] \d[A-Z]\d`. Per ulteriori informazioni sulle espressioni regolari, vedere [espressioni regolari di .NET Framework](../../../docs/standard/base-types/regular-expressions.md) e [esempi di espressioni regolari](../../../docs/standard/base-types/regular-expression-examples.md).  
  
-   Se il codice postale deve essere un codice postale degli Stati Uniti valido, è possibile chiamare un servizio Web di CAP per convalidare i dati immessi dall'utente.  
  
 Il <xref:System.Windows.Forms.Control.Validating> evento viene fornito un oggetto di tipo <xref:System.ComponentModel.CancelEventArgs>. Se si determina che i dati del controllo non sono validi, è possibile annullare il <xref:System.Windows.Forms.Control.Validating> evento mediante l'impostazione di questo oggetto <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà `true`. Se non si imposta la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> , Windows Form verrà si presuppone che la convalida ha avuto esito positivo per il controllo e generare il <xref:System.Windows.Forms.Control.Validated> evento.  
  
 Per un esempio di codice che convalida un indirizzo di posta elettronica in un <xref:System.Windows.Controls.TextBox>, vedere <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Data Binding e la convalida basata su eventi  
 La convalida è molto utile quando si hanno i controlli associati a un'origine dati, ad esempio una tabella di database. Mediante la convalida, è possibile assicurarsi che i dati del controllo soddisfino il formato richiesto dall'origine dati e che non contengano caratteri speciali come virgolette e barre rovesciate che potrebbe essere non sicure.  
  
 Quando si utilizza l'associazione dati, i dati nel controllo viene sincronizzati con l'origine dati durante l'esecuzione del <xref:System.Windows.Forms.Control.Validating> evento. Se si annulla la <xref:System.Windows.Forms.Control.Validating> eventi, i dati non verranno sincronizzati con l'origine dati.  
  
> [!IMPORTANT]
>  Se si dispone di convalida personalizzato che si verifica dopo il <xref:System.Windows.Forms.Control.Validating> evento, non avrà alcun effetto il data binding. Ad esempio, se si dispone di codice un <xref:System.Windows.Forms.Control.Validated> evento che tenta di annullare l'associazione dati, l'associazione dati continueranno a essere eseguiti. In questo caso, per eseguire la convalida nel <xref:System.Windows.Forms.Control.Validated> evento, impostare il controllo **modalità aggiornamento origine dati** proprietà (**in (Databindings)**\\ **(avanzate)** ) da **OnValidation** a **mai**e aggiungere *controllo*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` nel codice di convalida.  
  
### <a name="implicit-and-explicit-validation"></a>Convalida implicita ed esplicita  
 Pertanto, quando di un controllo vengono convalidati i dati? Questo è responsabilità dell'utente, lo sviluppatore. È possibile utilizzare la convalida può essere implicita o esplicita, a seconda delle esigenze dell'applicazione.  
  
#### <a name="implicit-validation"></a>Convalida implicita  
 La convalida implicita convalida i dati come l'utente immette il. È possibile convalidare i dati come i dati vengono immessi in un controllo, leggere le chiavi come vengono premuti, o più comunemente ogni volta che l'utente accetta lo stato attivo da un controllo e passa al successivo. Questo approccio è utile quando si desidera assegnare all'utente un feedback immediato sui dati che sta elaborando.  
  
 Se si desidera utilizzare la convalida implicita per un controllo, è necessario impostare tale controllo <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> proprietà `true`. Se si annulla la <xref:System.Windows.Forms.Control.Validating> evento, il comportamento del controllo verrà determinato dal valore assegnato a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Se è stato assegnato <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, l'evento di annullamento causerà il <xref:System.Windows.Forms.Control.Validated> evento non si verifichi. Stato attivo di input specificata resterà sul controllo corrente fino a quando l'utente modifica i dati in un input valido. Se è stato assegnato <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, <xref:System.Windows.Forms.Control.Validated> evento non verrà generato quando si annulla l'evento, ma lo stato attivo passerà al controllo successivo.  
  
 L'assegnazione di <xref:System.Windows.Forms.AutoValidate.Disable> per il <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> proprietà impedisce la convalida implicita completamente. Per convalidare i controlli, è necessario utilizzare la convalida esplicita.  
  
#### <a name="explicit-validation"></a>Convalida esplicita  
 La convalida esplicita convalida i dati in una sola volta. È possibile convalidare i dati in risposta a un'azione dell'utente, ad esempio facendo clic su un pulsante di salvataggio o un collegamento successivo. Quando si verifica l'azione dell'utente, è possibile attivare la convalida esplicita in uno dei modi seguenti:  
  
-   Chiamare <xref:System.Windows.Forms.ContainerControl.Validate%2A> per convalidare l'ultimo controllo di attivazione.  
  
-   Chiamare <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> per convalidare tutti i controlli figlio in un controllo form o del contenitore.  
  
-   Chiamare un metodo personalizzato per convalidare i dati nei controlli manualmente.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Controlli di convalida implicita predefinita per Windows Form  
 Diversi controlli Windows Form dispongono di valori predefiniti diversi per i relativi <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> proprietà. Nella tabella seguente mostra i controlli più comuni e sui valori predefiniti.  
  
|Control|Comportamento predefinito della convalida|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Proprietà non esposte in Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proprietà non esposte in Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Chiusura del Form e si esegue l'override di convalida  
 Quando un controllo mantiene lo stato attivo, perché i dati che contiene non sono validi, non è possibile chiudere il form padre in uno dei modi normale:  
  
-   Facendo clic di **Chiudi** pulsante.  
  
-   Selezionando **Chiudi** nel **sistema** menu.  
  
-   Chiamando il <xref:System.Windows.Forms.Form.Close%2A> metodo a livello di codice.  
  
 Tuttavia, in alcuni casi, è consigliabile consentire all'utente di chiudere il form indipendentemente dal fatto che i valori nei controlli sono validi. È possibile eseguire l'override di convalida e chiudere un form che contiene ancora dati non valido tramite la creazione di un gestore per il form <xref:System.Windows.Forms.Form.Closing> evento. Nell'evento, impostare il <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà `false`. Forza la chiusura del form. Per altre informazioni e un esempio, vedere <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Se si forza la chiusura in questo modo il form, i dati nei controlli del form non sono già stati salvati vengono persi. Inoltre, form modale non convalidano il contenuto dei controlli quando vengono chiusi. È comunque possibile utilizzare la convalida del controllo per bloccare lo stato attivo a un controllo, ma non è necessario considerare il comportamento associato alla chiusura del form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>  
 [Controllo MaskedTextBox](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)  
 [Esempi di espressioni regolari](../../../docs/standard/base-types/regular-expression-examples.md)
