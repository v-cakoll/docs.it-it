---
title: Caratteri internazionali in Windows Form e controlli
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
ms.openlocfilehash: b2738f174c9837a2ba83c1306f4617f39ce17de1
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208571"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="12c06-102">Caratteri internazionali in Windows Form e controlli</span><span class="sxs-lookup"><span data-stu-id="12c06-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="12c06-103">Nelle applicazioni internazionali, il metodo consigliato per la selezione del carattere è utilizzare il fallback laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="12c06-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="12c06-104">Per fallback si intende che il sistema determina quali il carattere di script a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="12c06-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="12c06-105">Tramite il fallback</span><span class="sxs-lookup"><span data-stu-id="12c06-105">Using font fallback</span></span>

<span data-ttu-id="12c06-106">Per sfruttare i vantaggi di questa funzionalità, non vengono impostate le <xref:System.Drawing.Font> proprietà per il form o qualsiasi altro elemento.</span><span class="sxs-lookup"><span data-stu-id="12c06-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="12c06-107">L'applicazione utilizzerà automaticamente il carattere di sistema predefinito, che differisce da una lingua localizzata del sistema operativo a un altro.</span><span class="sxs-lookup"><span data-stu-id="12c06-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="12c06-108">Quando viene eseguita l'applicazione, il sistema viene fornito automaticamente il tipo di carattere corretto per la lingua selezionata nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="12c06-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="12c06-109">È un'eccezione alla regola di non impostare il tipo di carattere, ovvero per modificare lo stile del carattere.</span><span class="sxs-lookup"><span data-stu-id="12c06-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="12c06-110">Questo potrebbe essere importante per un'applicazione in cui l'utente fa clic su un pulsante per visualizzare testo in una casella di testo in grassetto.</span><span class="sxs-lookup"><span data-stu-id="12c06-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="12c06-111">A tale scopo, è necessario scrivere una funzione per modificare lo stile del carattere della casella di testo da visualizzare in grassetto, in base a qualsiasi carattere del form è.</span><span class="sxs-lookup"><span data-stu-id="12c06-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="12c06-112">È importante chiamare questa funzione in due posizioni: il pulsante <xref:System.Windows.Forms.Control.Click> gestore dell'evento e il <xref:System.Windows.Forms.Control.FontChanged> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="12c06-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="12c06-113">Se la funzione viene chiamata solo nel <xref:System.Windows.Forms.Control.Click> gestore eventi e altre parti di codice cambia la famiglia di caratteri dell'intero form, la casella di testo non viene modificato con il resto del form.</span><span class="sxs-lookup"><span data-stu-id="12c06-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

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

<span data-ttu-id="12c06-114">Tuttavia, quando si localizza l'applicazione, il tipo di carattere grassetto potrebbe essere visualizzato in modo inadeguato per determinate lingue.</span><span class="sxs-lookup"><span data-stu-id="12c06-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="12c06-115">Se si tratta di un problema, si desidera che i localizzatori di hanno la possibilità di passare il tipo di carattere da grassetto in testo normale.</span><span class="sxs-lookup"><span data-stu-id="12c06-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="12c06-116">Poiché i localizzatori non sono in genere gli sviluppatori e non hanno accesso al codice sorgente, solo per i file di risorse, questa opzione deve essere impostata nei file di risorse.</span><span class="sxs-lookup"><span data-stu-id="12c06-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="12c06-117">A tale scopo, impostare il <xref:System.Drawing.Font.Bold%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="12c06-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="12c06-118">Ciò comporta l'impostazione del tipo di carattere viene scritto i file di risorse, in cui potrà essere modificata.</span><span class="sxs-lookup"><span data-stu-id="12c06-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="12c06-119">È quindi scrivere codice dopo il `InitializeComponent` per reimpostare il tipo di carattere dal qualsiasi carattere del form, ma utilizzando lo stile del carattere specificato nel file di risorse.</span><span class="sxs-lookup"><span data-stu-id="12c06-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="12c06-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12c06-120">See also</span></span>

[<span data-ttu-id="12c06-121">Globalizzazione di applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="12c06-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)  
[<span data-ttu-id="12c06-122">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="12c06-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)