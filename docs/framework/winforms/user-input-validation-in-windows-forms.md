---
title: Convalida dell'input utenteUser Input Validation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: eafbf54552566011fef9d2dbeb5e9f9fa3facabd
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646308"
---
# <a name="user-input-validation-in-windows-forms"></a>Convalida dell'input utente in Windows Form
Quando gli utenti immettono dati nell'applicazione, è possibile verificare che i dati siano validi prima che vengano utilizzati dall'applicazione. È possibile che alcuni campi di testo non siano di lunghezza zero, che un campo venga formattato come numero di telefono o altro tipo di dati in formato corretto o che una stringa non contenga caratteri non sicuri che potrebbero essere utilizzati per compromettere la sicurezza di un database. Windows Form offre diversi modi per convalidare l'input nell'applicazione.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Convalida con il controllo MaskedTextBoxValidation with the MaskedTextBox Control  
 Se è necessario richiedere agli utenti di immettere dati in un formato ben definito, ad esempio un numero <xref:System.Windows.Forms.MaskedTextBox> di telefono o un numero di parte, è possibile eseguire questa operazione in modo rapido e con codice minimo utilizzando il controllo. Una *maschera* è una stringa costituita da caratteri di un linguaggio di maschera che specifica quali caratteri possono essere immessi in una determinata posizione nella casella di testo. Il controllo visualizza un set di richieste all'utente. Se l'utente digita una voce errata, ad esempio, l'utente digita una lettera quando è necessaria una cifra, il controllo rifiuterà automaticamente l'input.  
  
 Il linguaggio di mascheramento utilizzato da <xref:System.Windows.Forms.MaskedTextBox> è molto flessibile. Consente di specificare caratteri obbligatori, caratteri facoltativi, caratteri letterali, ad esempio trattini e parentesi, caratteri di valuta e separatori di data. Il controllo funziona bene anche quando è associato a un'origine dati. L'evento <xref:System.Windows.Forms.Binding.Format> in un'associazione dati può essere utilizzato per riformattare i dati in ingresso in modo che siano conformi alla maschera e l'evento <xref:System.Windows.Forms.Binding.Parse> può essere utilizzato per riformattare i dati in uscita in modo che siano conformi alle specifiche del campo dati.  
  
 Per ulteriori informazioni, vedere [Controllo MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Convalida guidata da eventi  
 Se si desidera un controllo a livello di codice completo sulla convalida o è necessario eseguire controlli di convalida complessi, è necessario utilizzare gli eventi di convalida incorporati nella maggior parte dei controlli Windows Form. Ogni controllo che accetta l'input <xref:System.Windows.Forms.Control.Validating> dell'utente in formato libero dispone di un evento che si verifica ogni volta che il controllo richiede la convalida dei dati. Nel <xref:System.Windows.Forms.Control.Validating> metodo di gestione degli eventi, è possibile convalidare l'input dell'utente in diversi modi. Ad esempio, se si dispone di una casella di testo che deve contenere un codice postale, è possibile eseguire la convalida nei modi seguenti:For example, if you have a text box that must contain a postal code, you can perform the validation in the following ways:  
  
- Se il codice postale deve appartenere a un gruppo specifico di codici postali, è possibile eseguire un confronto tra stringhe sull'input per convalidare i dati immessi dall'utente. Ad esempio, se il codice postale deve essere nel set 10001, 10002, 10003, è possibile utilizzare un confronto tra stringhe per convalidare i dati.  
  
- Se il codice postale deve essere in una forma specifica, è possibile utilizzare espressioni regolari per convalidare i dati immessi dall'utente. Ad esempio, per `#####` convalidare il modulo oppure `#####-####`, è possibile utilizzare l'espressione `^(\d{5})(-\d{4})?$`regolare . Per convalidare `A#A #A#`il modulo, è `[A-Z]\d[A-Z] \d[A-Z]\d`possibile utilizzare l'espressione regolare . Per ulteriori informazioni sulle espressioni regolari, vedere [Espressioni regolari di .NET Framework](../../standard/base-types/regular-expressions.md) ed esempi di espressioni [regolari](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md).  
  
- Se il codice postale deve essere un codice postale valido per gli Stati Uniti, è possibile chiamare un servizio Web di codice postale per convalidare i dati immessi dall'utente.  
  
 All'evento <xref:System.Windows.Forms.Control.Validating> viene fornito un <xref:System.ComponentModel.CancelEventArgs>oggetto di tipo . Se si determina che i dati del controllo non <xref:System.Windows.Forms.Control.Validating> sono validi, è <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> possibile `true`annullare l'evento impostando la proprietà di questo oggetto su . Se non si <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> imposta la proprietà , Windows Form presupporrà <xref:System.Windows.Forms.Control.Validated> che la convalida abbia esito positivo per il controllo e genererà l'evento .  
  
 Per un esempio di codice che <xref:System.Windows.Controls.TextBox>convalida <xref:System.Windows.Forms.Control.Validating>un indirizzo di posta elettronica in un oggetto , vedere .  
  
### <a name="data-binding-and-event-driven-validation"></a>Associazione dati e convalida guidata da eventiData Binding and Event-Driven Validation  
 La convalida è molto utile quando i controlli sono stati associati a un'origine dati, ad esempio una tabella di database. Utilizzando la convalida, è possibile assicurarsi che i dati del controllo soddisfino il formato richiesto dall'origine dati e che non contenga caratteri speciali, ad esempio virgolette e barre rovesciate che potrebbero non essere sicuri.  
  
 Quando si utilizza l'associazione dati, i dati nel controllo <xref:System.Windows.Forms.Control.Validating> vengono sincronizzati con l'origine dati durante l'esecuzione dell'evento. Se si <xref:System.Windows.Forms.Control.Validating> annulla l'evento, i dati non verranno sincronizzati con l'origine dati.  
  
> [!IMPORTANT]
> Se si dispone di una <xref:System.Windows.Forms.Control.Validating> convalida personalizzata che viene eseguita dopo l'evento, non influirà sull'associazione dati. Ad esempio, se si <xref:System.Windows.Forms.Control.Validated> dispone di codice in un evento che tenta di annullare l'associazione dati, l'associazione dati si verificherà comunque. In questo caso, per <xref:System.Windows.Forms.Control.Validated> eseguire la convalida nell'evento, modificare la proprietà **Data Source Update Mode** del controllo ( in **(Databindings)**\\ **(Advanced)**) da **OnValidation** a **Never**e aggiungere *Control*`.DataBindings["`*\<YOURFIELD>* `"].WriteValue()` al codice di convalida.  
  
### <a name="implicit-and-explicit-validation"></a>Convalida implicita ed esplicita  
 Pertanto, quando vengono convalidati i dati di un controllo? Questo è a voi, lo sviluppatore. È possibile utilizzare la convalida implicita o esplicita, a seconda delle esigenze dell'applicazione.  
  
#### <a name="implicit-validation"></a>Convalida implicita  
 L'approccio di convalida implicita convalida i dati quando l'utente li immette. È possibile convalidare i dati quando i dati vengono immessi in un controllo leggendo i tasti mentre vengono premuti o più comunemente ogni volta che l'utente distoglie lo stato attivo per l'input da un controllo e passa a quello successivo. Questo approccio è utile quando si desidera fornire all'utente un feedback immediato sui dati mentre lavorano.  
  
 Se si desidera utilizzare la convalida implicita per un <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> controllo, è necessario impostare la proprietà del controllo su <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> o <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>. Se si <xref:System.Windows.Forms.Control.Validating> annulla l'evento, il comportamento del controllo sarà <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>determinato dal valore assegnato a . Se è <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>stato assegnato , l'annullamento dell'evento causerà la non occorrenza dell'evento. <xref:System.Windows.Forms.Control.Validated> Lo stato attivo per l'input rimarrà sul controllo corrente fino a quando l'utente non modifica i dati in un input valido. Se è <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>stato <xref:System.Windows.Forms.Control.Validated> assegnato , l'evento non si verificherà quando si annulla l'evento, ma lo stato attivo passa comunque al controllo successivo.  
  
 <xref:System.Windows.Forms.AutoValidate.Disable> L'assegnazione <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> alla proprietà impedisce del tutto la convalida implicita. Per convalidare i controlli, è necessario utilizzare la convalida esplicita.  
  
#### <a name="explicit-validation"></a>Convalida esplicitaExplicit Validation  
 L'approccio di convalida esplicita convalida i dati contemporaneamente. È possibile convalidare i dati in risposta a un'azione dell'utente, ad esempio facendo clic su un pulsante Salva o su un collegamento Avanti. Quando si verifica l'azione dell'utente, è possibile attivare la convalida esplicita in uno dei modi seguenti:  
  
- Chiamata <xref:System.Windows.Forms.ContainerControl.Validate%2A> per convalidare l'ultimo controllo che ha perso lo stato attivo.  
  
- Chiamata <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> per convalidare tutti i controlli figlio in un form o un controllo contenitore.  
  
- Chiamare manualmente un metodo personalizzato per convalidare manualmente i dati nei controlli.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Comportamento di convalida implicito predefinito per i controlli Windows FormDefault Implicit Validation Behavior for Windows Forms Controls  
 Controlli Windows Form diversi hanno <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> valori predefiniti diversi per la proprietà. Nella tabella seguente vengono illustrati i controlli più comuni e i relativi valori predefiniti.  
  
|Controllo|Comportamento di convalida predefinitoDefault Validation Behavior|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Proprietà non esposta in Visual StudioProperty not exposed in Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proprietà non esposta in Visual StudioProperty not exposed in Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Chiusura del modulo e della convalida di override  
 Quando un controllo mantiene lo stato attivo perché i dati in esso contenuti non sono validi, è impossibile chiudere il form padre in uno dei modi seguenti:  
  
- Facendo clic sul pulsante **Chiudi.**  
  
- Selezionando **Chiudi** nel menu **Sistema.**  
  
- Chiamando il <xref:System.Windows.Forms.Form.Close%2A> metodo a livello di codice.  
  
 Tuttavia, in alcuni casi, è possibile consentire all'utente di chiudere il form indipendentemente dal fatto che i valori nei controlli siano validi. È possibile eseguire l'override della convalida e chiudere un form <xref:System.Windows.Forms.Form.FormClosing> che contiene ancora dati non validi creando un gestore per l'evento del form. Nell'evento, impostare `false`la proprietà su <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> . In questo modo il form viene chiuso. Per altre informazioni e un esempio, vedere <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>.  
  
> [!NOTE]
> Se si forza la chiusura del modulo in questo modo, tutti i dati nei controlli del modulo che non sono già stati salvati andranno persi. Inoltre, i form modali non convalidano il contenuto dei controlli quando vengono chiusi. È comunque possibile utilizzare la convalida del controllo per bloccare lo stato attivo su un controllo, ma non è necessario preoccuparsi del comportamento associato alla chiusura del form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [Controllo MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md)
- [Esempi di espressioni regolari](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)
