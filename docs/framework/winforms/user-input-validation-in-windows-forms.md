---
title: Convalida dell'input dell'utente
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: dc56c09677d1054e8f264169b78638fa83bd7d9e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734685"
---
# <a name="user-input-validation-in-windows-forms"></a>Convalida dell'input utente in Windows Form
Quando gli utenti immettono dati nell'applicazione, è consigliabile verificare che i dati siano validi prima che l'applicazione lo usi. Potrebbe essere necessario che determinati campi di testo non siano di lunghezza zero, che un campo venga formattato come numero di telefono o altro tipo di dati ben formati o che una stringa non contenga caratteri non sicuri che potrebbero essere usati per compromettere la sicurezza di un database. Windows Forms offre diversi modi per convalidare l'input nell'applicazione.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Convalida con il controllo MaskedTextBox  
 Se è necessario richiedere agli utenti di immettere dati in un formato ben definito, ad esempio un numero di telefono o un numero di parte, è possibile eseguire questa operazione rapidamente e con codice minimo usando il controllo <xref:System.Windows.Forms.MaskedTextBox>. Una *maschera* è una stringa costituita da caratteri di un linguaggio di mascheramento che specifica i caratteri che possono essere immessi in una determinata posizione nella casella di testo. Il controllo Visualizza un set di richieste all'utente. Se l'utente digita una voce non corretta, ad esempio, l'utente digita una lettera quando è richiesta una cifra, il controllo rifiuterà automaticamente l'input.  
  
 Il linguaggio di mascheramento utilizzato da <xref:System.Windows.Forms.MaskedTextBox> è molto flessibile. Consente di specificare i caratteri obbligatori, i caratteri facoltativi, i caratteri letterali, ad esempio trattini e parentesi, caratteri di valuta e separatori di data. Il controllo funziona anche correttamente quando è associato a un'origine dati. L'evento <xref:System.Windows.Forms.Binding.Format> in un data binding può essere utilizzato per riformattare i dati in ingresso in modo che siano conformi alla maschera e l'evento <xref:System.Windows.Forms.Binding.Parse> può essere utilizzato per riformattare i dati in uscita in modo che siano conformi alle specifiche del campo dati.  
  
 Per altre informazioni, vedere [controllo MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Convalida guidata dagli eventi  
 Se si desidera controllare completamente a livello di codice la convalida o eseguire controlli di convalida complessi, è necessario utilizzare gli eventi di convalida incorporati nella maggior parte dei controlli Windows Forms. Ogni controllo che accetta input utente in formato libero ha un evento <xref:System.Windows.Forms.Control.Validating> che si verificherà ogni volta che il controllo richiede la convalida dei dati. Nel metodo di gestione degli eventi <xref:System.Windows.Forms.Control.Validating> è possibile convalidare l'input dell'utente in diversi modi. Ad esempio, se si dispone di una casella di testo che deve contenere un CAP, è possibile eseguire la convalida nei modi seguenti:  
  
- Se il codice postale deve appartenere a un gruppo specifico di codici postali, è possibile eseguire un confronto tra stringhe sull'input per convalidare i dati immessi dall'utente. Se, ad esempio, il codice postale deve essere nel set {10001, 10002, 10003}, è possibile usare un confronto tra stringhe per convalidare i dati.  
  
- Se il codice postale deve essere in un formato specifico, è possibile utilizzare le espressioni regolari per convalidare i dati immessi dall'utente. Ad esempio, per convalidare il form `#####` o `#####-####`, è possibile usare l'espressione regolare `^(\d{5})(-\d{4})?$`. Per convalidare il modulo `A#A #A#`, è possibile usare l'`[A-Z]\d[A-Z] \d[A-Z]\d`di espressioni regolari. Per ulteriori informazioni sulle espressioni regolari, vedere [.NET Framework espressioni regolari](../../standard/base-types/regular-expressions.md) ed [esempi](../../standard/base-types/regular-expression-examples.md)di espressioni regolari.  
  
- Se il codice postale deve essere un Stati Uniti CAP valido, è possibile chiamare un servizio Web di codice postale per convalidare i dati immessi dall'utente.  
  
 All'evento <xref:System.Windows.Forms.Control.Validating> viene fornito un oggetto di tipo <xref:System.ComponentModel.CancelEventArgs>. Se si determina che i dati del controllo non sono validi, è possibile annullare l'evento <xref:System.Windows.Forms.Control.Validating> impostando la proprietà <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> dell'oggetto su `true`. Se non si imposta la proprietà <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>, Windows Forms presuppone che la convalida abbia esito positivo per tale controllo e generi l'evento <xref:System.Windows.Forms.Control.Validated>.  
  
 Per un esempio di codice che convalida un indirizzo di posta elettronica in un <xref:System.Windows.Controls.TextBox>, vedere <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Associazione dati e convalida basata su eventi  
 La convalida è molto utile quando i controlli vengono associati a un'origine dati, ad esempio una tabella di database. Utilizzando la convalida, è possibile verificare che i dati del controllo soddisfino il formato richiesto dall'origine dati e che non contenga caratteri speciali, ad esempio virgolette e barre rovesciate che potrebbero non essere sicure.  
  
 Quando si utilizza data binding, i dati nel controllo vengono sincronizzati con l'origine dati durante l'esecuzione dell'evento <xref:System.Windows.Forms.Control.Validating>. Se si annulla l'evento <xref:System.Windows.Forms.Control.Validating>, i dati non verranno sincronizzati con l'origine dati.  
  
> [!IMPORTANT]
> Se si dispone di una convalida personalizzata che si verifica dopo l'evento <xref:System.Windows.Forms.Control.Validating>, non influirà sui data binding. Se, ad esempio, si dispone di codice in un evento <xref:System.Windows.Forms.Control.Validated> che tenta di annullare l'data binding, il data binding continuerà a verificarsi. In questo caso, per eseguire la convalida nell'evento <xref:System.Windows.Forms.Control.Validated>, modificare la proprietà **modalità di aggiornamento dell'origine dati** del controllo (**in (DataBindings)** \\ **(avanzate)** ) da **OnValidation** a **Never**e aggiungere *Control*`.DataBindings["` *\<campo >* `"].WriteValue()` al codice di convalida.  
  
### <a name="implicit-and-explicit-validation"></a>Convalida implicita ed esplicita  
 Quando vengono convalidati i dati di un controllo? Questo è lo sviluppatore. È possibile usare la convalida implicita o esplicita, a seconda delle esigenze dell'applicazione.  
  
#### <a name="implicit-validation"></a>Convalida implicita  
 L'approccio di convalida implicita convalida i dati quando l'utente lo immette. È possibile convalidare i dati quando i dati vengono immessi in un controllo leggendo le chiavi quando vengono premuti oppure, più comunemente, ogni volta che l'utente preleva lo stato attivo di input da un controllo e passa a quello successivo. Questo approccio è utile quando si desidera fornire all'utente un feedback immediato sui dati man mano che funzionano.  
  
 Se si vuole usare la convalida implicita per un controllo, è necessario impostare la proprietà <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> del controllo su <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> o <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>. Se si annulla l'evento <xref:System.Windows.Forms.Control.Validating>, il comportamento del controllo sarà determinato dal valore assegnato a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Se è stato assegnato <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, l'annullamento dell'evento causerà la mancata esecuzione dell'evento <xref:System.Windows.Forms.Control.Validated>. Lo stato attivo per l'input rimarrà sul controllo corrente fino a quando l'utente non modifica i dati in un input valido. Se è stato assegnato <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, l'evento <xref:System.Windows.Forms.Control.Validated> non si verificherà quando si annulla l'evento, ma lo stato attivo continuerà a passare al controllo successivo.  
  
 L'assegnazione di <xref:System.Windows.Forms.AutoValidate.Disable> alla proprietà <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> impedisce completamente la convalida implicita. Per convalidare i controlli, sarà necessario usare la convalida esplicita.  
  
#### <a name="explicit-validation"></a>Convalida esplicita  
 L'approccio di convalida esplicita convalida i dati in una sola volta. È possibile convalidare i dati in risposta a un'azione dell'utente, ad esempio facendo clic su un pulsante Salva o su un collegamento successivo. Quando si verifica l'azione dell'utente, è possibile attivare la convalida esplicita in uno dei modi seguenti:  
  
- Chiamare <xref:System.Windows.Forms.ContainerControl.Validate%2A> per convalidare l'ultimo controllo in modo che abbia perso lo stato attivo.  
  
- Chiamare <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> per convalidare tutti i controlli figlio in un form o in un controllo contenitore.  
  
- Chiamare un metodo personalizzato per convalidare manualmente i dati nei controlli.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Comportamento predefinito della convalida implicita per i controlli Windows Forms  
 Diversi controlli di Windows Forms hanno impostazioni predefinite diverse per la relativa proprietà <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. La tabella seguente illustra i controlli più comuni e le relative impostazioni predefinite.  
  
|Control|Comportamento di convalida predefinito|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Proprietà non esposta in Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proprietà non esposta in Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Chiusura del form e override della convalida  
 Quando un controllo mantiene lo stato attivo perché i dati in esso contenuti non sono validi, non è possibile chiudere il form padre in uno dei modi usuali:  
  
- Facendo clic sul pulsante **Chiudi** .  
  
- Selezionando **Chiudi** nel menu **sistema** .  
  
- Chiamando il metodo <xref:System.Windows.Forms.Form.Close%2A> a livello di codice.  
  
 In alcuni casi, tuttavia, potrebbe essere necessario lasciare che l'utente chiuda il form indipendentemente dal fatto che i valori nei controlli siano validi. È possibile eseguire l'override della convalida e chiudere un modulo che contiene ancora dati non validi creando un gestore per l'evento <xref:System.Windows.Forms.Form.FormClosing> del modulo. Nell'evento, impostare la proprietà <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> su `false`. Questa operazione impone la chiusura del form. Per altre informazioni e un esempio, vedere <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>.  
  
> [!NOTE]
> Se si impone la chiusura del form in questo modo, tutti i dati nei controlli del form che non sono già stati salvati andranno persi. Inoltre, i form modali non convalidano il contenuto dei controlli quando vengono chiusi. È comunque possibile usare la convalida dei controlli per bloccare lo stato attivo su un controllo, ma non è necessario preoccuparsi del comportamento associato alla chiusura del modulo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [Controllo MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md)
- [Esempi di espressioni regolari](../../standard/base-types/regular-expression-examples.md)
