---
title: 'Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 804041991199dd2722e3a0f38800bafd8933bbab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333665"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito

È possibile utilizzare gli stili in formato HTML per controllare l'aspetto di un documento e i relativi elementi. <xref:System.Windows.Forms.HtmlDocument> e <xref:System.Windows.Forms.HtmlElement> supportano <xref:System.Windows.Forms.HtmlElement.Style%2A> proprietà che accettano stringhe di tipo nel formato seguente:

`name1:value1;...;nameN:valueN;`

Di seguito è riportato un `DIV` con una stringa di stile che imposta il tipo di carattere Arial e tutto il testo in grassetto:

`<DIV style="font-face:arial;font-weight:bold;">`

`Hello, world!`

`</DIV>`

Il problema con la modifica degli stili utilizzando il <xref:System.Windows.Forms.HtmlElement.Style%2A> proprietà è che può rivelarsi complesso da aggiungere e rimuovere singole impostazioni di stile dalla stringa. Ad esempio, diventa una procedura complessa per l'utente per il rendering del testo precedente in corsivo ogni volta che l'utente posiziona il cursore sul `DIV`e sfruttare corsivo quando il cursore viene spostato dalla `DIV`. Ora diventa un problema se è necessario gestire un numero elevato di stili in questo modo.

La procedura seguente contiene codice che è possibile usare per gestire facilmente stili in documenti HTML e gli elementi. La procedura richiede di conoscere le procedure eseguire le attività di base in Windows Form, ad esempio creando un nuovo progetto e aggiungere un controllo a un form.

### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Per elaborare le modifiche di stile di visualizzazione in un'applicazione Windows Forms

1. Creare un nuovo progetto Windows Form.

2. Creare un nuovo file di classe che terminano con l'estensione appropriata per il linguaggio di programmazione.

3. Copia il `StyleGenerator` codice nella sezione esempio di questo argomento della classe nel file di classe e salvare il codice.

4. Salvare il codice HTML seguente in un file denominato test. htm.

    ```html
    <HTML>
        <BODY>

            <DIV style="font-face:arial;font-weight:bold;">
                Hello, world!
            </DIV><P>

            <DIV>
                Hello again, world!
            </DIV><P>

        </BODY>
    </HTML>
    ```

5. Aggiungere un <xref:System.Windows.Forms.WebBrowser> controllo denominato `webBrowser1` al modulo principale del progetto.

6. Aggiungere il codice seguente al file di codice del progetto.

    > [!IMPORTANT]
    >  Verificare che il `webBrowser1_DocumentCompleted` gestore dell'evento è configurato come un listener per il <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento. In Visual Studio, fare doppio clic su di <xref:System.Windows.Forms.WebBrowser> controllo; in un editor di testo, configurare il listener a livello di codice.  
  
     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7. Eseguire il progetto. Spostare il cursore sul primo `DIV` e osservare gli effetti del codice.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato il codice completo per il `StyleGenerator` (classe), che analizza un valore di stile esistente, supporta l'aggiunta, modifica e rimozione di stili e restituisce un nuovo valore di stile con le modifiche richieste.  
  
 [!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.HtmlElement>
