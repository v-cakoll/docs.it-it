---
title: Convalida dell'input utente in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: c8a40706df4274728b438cff2539173a0e94b767
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800126"
---
# <a name="user-input-validation-in-windows-forms"></a>Convalida dell'input utente in Windows Form
Quando gli utenti immettono dati nell'applicazione, è possibile verificare che i dati siano validi prima che vengano utilizzati dall'applicazione. Potrebbe essere necessario che alcuni campi di testo non essere a lunghezza zero, che un campo formattato come un numero di telefono o altro tipo di dati in formato corretto o che una stringa non contenga caratteri non sicuri che può essere usati per compromettere la protezione di un database. Windows Form fornisce diversi metodi per convalidare l'input nell'applicazione.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Convalida del controllo MaskedTextBox  
 Se è necessario richiedere agli utenti di immettere i dati in un formato ben definito, ad esempio un numero di telefono o un numero di parte, è possibile farlo rapidamente e con quantità minima di codice usando il <xref:System.Windows.Forms.MaskedTextBox> controllo. Oggetto *mask* è una stringa costituita da caratteri in un linguaggio di definizione della maschera che specifica i caratteri che possono essere inseriti in una posizione specificata nella casella di testo. Il controllo Visualizza una serie di richieste all'utente. Se l'utente digita una voce non valida, ad esempio, l'utente digita una lettera di quando è necessaria una cifra, il controllo verrà rifiutato automaticamente l'input.  
  
 Il linguaggio di mascheramento che viene usato da <xref:System.Windows.Forms.MaskedTextBox> è molto flessibile. Consente di specificare caratteri necessari, caratteri facoltativi, i caratteri letterali, ad esempio trattini e parentesi, valuta caratteri e separatori di Data. Il controllo funziona anche quando è associato a un'origine dati. Il <xref:System.Windows.Forms.Binding.Format> evento su un'associazione di dati può essere utilizzato per riformattare i dati in ingresso per garantire la conformità con la maschera e <xref:System.Windows.Forms.Binding.Parse> evento può essere utilizzato per riformattare i dati in uscita per garantire la conformità con le specifiche del campo dati.  
  
 Per altre informazioni, vedere [controllo MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Convalida basata su eventi  
 Se si vuole il controllo completo a livello di codice sulla convalida, o necessario eseguire controlli di convalida complessi, si devono usare gli eventi di convalida incorporati in maggior parte dei controlli Windows Form. Ogni controllo che accetta l'input dell'utente in formato libero ha un <xref:System.Windows.Forms.Control.Validating> evento che si verifica ogni volta che il controllo richiede la convalida dei dati. Nel <xref:System.Windows.Forms.Control.Validating> metodo di gestione degli eventi, è possibile convalidare l'input dell'utente in diversi modi. Ad esempio, se si dispone di una casella di testo che deve contenere un codice postale, è possibile eseguire la convalida nei modi seguenti:  
  
- Se il codice postale deve appartenere a un gruppo specifico di codici postali, è possibile eseguire un confronto tra stringhe di input per convalidare i dati immessi dall'utente. Ad esempio, se nel set di {10001 e 10002 10003} deve essere il codice postale, quindi è possibile utilizzare un confronto tra stringhe per convalidare i dati.  
  
- Se il codice postale deve avere un formato specifico è possibile usare espressioni regolari per convalidare i dati immessi dall'utente. Ad esempio, per convalidare il modulo `#####` oppure `#####-####`, è possibile usare l'espressione regolare `^(\d{5})(-\d{4})?$`. Per convalidare il modulo `A#A #A#`, è possibile usare l'espressione regolare `[A-Z]\d[A-Z] \d[A-Z]\d`. Per altre informazioni sulle espressioni regolari, vedere [espressioni regolari di .NET Framework](../../standard/base-types/regular-expressions.md) e [esempi di espressioni regolari](../../standard/base-types/regular-expression-examples.md).  
  
- Se il codice postale deve essere un codice postale degli Stati Uniti valido, è possibile chiamare un servizio Web di CAP per convalidare i dati immessi dall'utente.  
  
 Il <xref:System.Windows.Forms.Control.Validating> evento viene fornito un oggetto di tipo <xref:System.ComponentModel.CancelEventArgs>. Se si determina che i dati del controllo non sono validi, è possibile annullare il <xref:System.Windows.Forms.Control.Validating> evento mediante l'impostazione dell'oggetto <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà `true`. Se non si impostano i <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà, Windows Form verrà presuppongono che la convalida ha avuto esito positivo per il controllo e generare il <xref:System.Windows.Forms.Control.Validated> evento.  
  
 Per un esempio di codice che convalida un indirizzo di posta elettronica in un <xref:System.Windows.Controls.TextBox>, vedere <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Data Binding e la convalida basata su eventi  
 La convalida è molto utile quando si sono associati i controlli a un'origine dati, ad esempio una tabella di database. Mediante la convalida, è possibile assicurarsi che i dati del controllo soddisfano il formato richiesto dall'origine dati e che non contengono caratteri speciali, ad esempio racchiusi tra virgolette e barre rovesciate che potrebbe essere non sicuro.  
  
 Quando si usa l'associazione dati, i dati nel controllo viene sincronizzati con l'origine dati durante l'esecuzione del <xref:System.Windows.Forms.Control.Validating> evento. Se si annulla la <xref:System.Windows.Forms.Control.Validating> eventi, i dati non verranno sincronizzati con l'origine dati.  
  
> [!IMPORTANT]
>  Se si dispone di convalida personalizzata che ha luogo dopo la <xref:System.Windows.Forms.Control.Validating> evento, non avrà alcun effetto il data binding. Ad esempio, se si dispone di codice un <xref:System.Windows.Forms.Control.Validated> evento che tenta di annullare l'associazione dati, il data binding verrà ancora generato. In questo caso, per eseguire la convalida nel <xref:System.Windows.Forms.Control.Validated> evento, il controllo delle modifiche **modalità aggiornamento origine dati** proprietà (**sotto (Databindings)**\\ **(avanzate)** ) da **OnValidation** al **Never**, quindi aggiungere *controllo*`.DataBindings["`*\<campo >*  `"].WriteValue()` nel codice di convalida.  
  
### <a name="implicit-and-explicit-validation"></a>Convalida implicita ed esplicita  
 Pertanto, quando di un controllo vengono convalidati i dati? Ciò è responsabilità dell'utente, lo sviluppatore. È possibile usare la convalida implicita o esplicita, a seconda delle esigenze dell'applicazione.  
  
#### <a name="implicit-validation"></a>Convalida implicita  
 La convalida implicita convalida dei dati quando l'utente ne immette lo. È possibile convalidare i dati come i dati vengono immessi in un controllo, leggere le chiavi come vengono premuti, o più comunemente ogni volta che l'utente accetta l'input lo stato attivo da un controllo e passa al successivo. Questo approccio è utile quando si desidera assegnare all'utente un feedback immediato sui dati che sta elaborando.  
  
 Se si desidera utilizzare la convalida implicita per un controllo, è necessario impostare che controllano <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> proprietà `true`. Se si annulla la <xref:System.Windows.Forms.Control.Validating> evento, il comportamento del controllo verrà determinato dal valore assegnato a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Se è stato assegnato <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, l'evento di annullamento causerà il <xref:System.Windows.Forms.Control.Validated> evento non si verifichi. Lo stato attivo input rimarranno sul controllo corrente fino a quando l'utente modifica i dati in un formato valido. Se è stato assegnato <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, il <xref:System.Windows.Forms.Control.Validated> evento non si verificherà quando si annulla l'evento, ma lo stato attivo passerà al controllo successivo.  
  
 Assegnazione <xref:System.Windows.Forms.AutoValidate.Disable> per il <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> proprietà impedisce la convalida implicita del tutto. Per convalidare i controlli, è necessario utilizzare la convalida esplicita.  
  
#### <a name="explicit-validation"></a>Convalida esplicita  
 L'approccio esplicito convalida convalida dei dati in una sola volta. È possibile convalidare i dati in risposta a un'azione dell'utente, ad esempio la selezione di un pulsante di salvataggio o un collegamento successivo. Quando si verifica l'azione dell'utente, è possibile attivare la convalida esplicita in uno dei modi seguenti:  
  
- Chiamare <xref:System.Windows.Forms.ContainerControl.Validate%2A> per convalidare l'ultimo controllo nello stato di attivazione.  
  
- Chiamare <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> per convalidare tutti i controlli figlio in un form o un controllo contenitore.  
  
- Chiamare un metodo personalizzato per convalidare i dati nei controlli manualmente.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Controlli di convalida implicita predefinita per Windows Form  
 I diversi controlli Windows Form hanno diverse impostazioni predefinite per loro <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> proprietà. La tabella seguente illustra i controlli più comuni e sui valori predefiniti.  
  
|Control|Comportamento predefinito della convalida|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Proprietà non esposte in Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proprietà non esposte in Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Chiusura del Form e si esegue l'override di convalida  
 Quando un controllo mantiene lo stato attivo perché i dati che contiene non sono validi, non è possibile chiudere il form padre in uno dei modi consueto:  
  
- Facendo clic la **Chiudi** pulsante.  
  
- Selezionando **Close** nel **sistema** menu.  
  
- Chiamando il <xref:System.Windows.Forms.Form.Close%2A> metodo a livello di codice.  
  
 Tuttavia, in alcuni casi, potrebbe voler consentire all'utente di chiudere il modulo indipendentemente dal fatto che i valori nei controlli sono validi. È possibile eseguire l'override di convalida e chiudere un modulo che contiene ancora dati non valido tramite la creazione di un gestore per il form <xref:System.Windows.Forms.Form.Closing> evento. Nell'evento, impostare il <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà `false`. Forza la chiusura del form. Per altre informazioni e un esempio, vedere <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Se si forza la chiusura in questo modo il form, i dati nei controlli del modulo che non sono già stati salvati vanno persi. Inoltre, i form modali non convalidano il contenuto dei controlli quando vengono chiusi. È comunque possibile usare la convalida del controllo per bloccare lo stato attivo a un controllo, ma non è importante il comportamento associato chiudendo il form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>
- <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>
- [Controllo MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md)
- [Esempi di espressioni regolari](../../standard/base-types/regular-expression-examples.md)
