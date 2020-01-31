---
title: Tipi di carattere internazionali nei form e nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743513"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="c7fce-102">Tipi di carattere internazionali in Windows Forms e controlli</span><span class="sxs-lookup"><span data-stu-id="c7fce-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="c7fce-103">Nelle applicazioni internazionali, il metodo consigliato per la selezione di tipi di carattere consiste nell'usare il fallback del tipo di carattere laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="c7fce-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="c7fce-104">Il fallback del tipo di carattere significa che il sistema determina a quale script appartiene il carattere.</span><span class="sxs-lookup"><span data-stu-id="c7fce-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="c7fce-105">Uso del fallback dei tipi di carattere</span><span class="sxs-lookup"><span data-stu-id="c7fce-105">Using font fallback</span></span>

<span data-ttu-id="c7fce-106">Per sfruttare i vantaggi di questa funzionalità, non impostare la proprietà <xref:System.Drawing.Font> per il form o qualsiasi altro elemento.</span><span class="sxs-lookup"><span data-stu-id="c7fce-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="c7fce-107">L'applicazione userà automaticamente il tipo di carattere di sistema predefinito, che differisce da una lingua localizzata del sistema operativo a un'altra.</span><span class="sxs-lookup"><span data-stu-id="c7fce-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="c7fce-108">Quando l'applicazione viene eseguita, il sistema fornisce automaticamente il tipo di carattere corretto per le impostazioni cultura selezionate nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c7fce-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="c7fce-109">Si verifica un'eccezione alla regola di non impostare il tipo di carattere, ovvero per modificare lo stile del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="c7fce-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="c7fce-110">Questo potrebbe essere importante per un'applicazione in cui l'utente fa clic su un pulsante per creare il testo in una casella di testo in grassetto.</span><span class="sxs-lookup"><span data-stu-id="c7fce-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="c7fce-111">A tale scopo, è necessario scrivere una funzione per modificare lo stile del tipo di carattere della casella di testo in grassetto, in base a qualsiasi tipo di carattere del modulo.</span><span class="sxs-lookup"><span data-stu-id="c7fce-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="c7fce-112">È importante chiamare questa funzione in due posizioni: nel gestore dell'evento <xref:System.Windows.Forms.Control.Click> del pulsante e nel gestore dell'evento <xref:System.Windows.Forms.Control.FontChanged>.</span><span class="sxs-lookup"><span data-stu-id="c7fce-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="c7fce-113">Se la funzione viene chiamata solo nel gestore eventi <xref:System.Windows.Forms.Control.Click> e alcune altre parti di codice modificano la famiglia di caratteri dell'intero form, la casella di testo non cambia con il resto del modulo.</span><span class="sxs-lookup"><span data-stu-id="c7fce-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="c7fce-114">Tuttavia, quando si localizza l'applicazione, il tipo di carattere in grassetto potrebbe risultare scarso per alcune lingue.</span><span class="sxs-lookup"><span data-stu-id="c7fce-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="c7fce-115">Se si tratta di un problema, si desidera che i localizzatori abbiano la possibilità di cambiare il tipo di carattere da grassetto a testo normale.</span><span class="sxs-lookup"><span data-stu-id="c7fce-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="c7fce-116">Poiché i localizzatori non sono in genere sviluppatori e non hanno accesso al codice sorgente, solo ai file di risorse, questa opzione deve essere impostata nei file di risorse.</span><span class="sxs-lookup"><span data-stu-id="c7fce-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="c7fce-117">A tale scopo, impostare la proprietà <xref:System.Drawing.Font.Bold%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="c7fce-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="c7fce-118">In questo modo, l'impostazione del tipo di carattere viene scritta nei file di risorse, in cui i localizzatori possono modificarlo.</span><span class="sxs-lookup"><span data-stu-id="c7fce-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="c7fce-119">Si scrive quindi il codice dopo il metodo `InitializeComponent` per reimpostare il tipo di carattere in base a qualsiasi tipo di carattere del form, ma usando lo stile del carattere specificato nel file di risorse.</span><span class="sxs-lookup"><span data-stu-id="c7fce-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="c7fce-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7fce-120">See also</span></span>

- [<span data-ttu-id="c7fce-121">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="c7fce-121">Using Fonts and Text</span></span>](using-fonts-and-text.md)
