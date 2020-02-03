---
title: Ridimensiona form
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 8d4ce46ada505f952fc3090d10c5d893338d19f2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739312"
---
# <a name="how-to-resize-windows-forms"></a>Procedura: Ridimensionare Windows Form

È possibile specificare le dimensioni del Windows Form in diversi modi. È possibile modificare sia l'altezza che la larghezza del form a livello di codice impostando un nuovo valore per la proprietà <xref:System.Windows.Forms.Form.Size%2A> o modificare le singole proprietà <xref:System.Windows.Forms.Control.Height%2A> o <xref:System.Windows.Forms.Control.Width%2A>. Se si usa Visual Studio, è possibile modificare le dimensioni usando il Progettazione Windows Form. Vedere anche [procedura: ridimensionare Windows Forms usando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).

## <a name="resize-a-form-programmatically"></a>Ridimensionare un form a livello di codice

Definire le dimensioni di un form in fase di esecuzione impostando la proprietà <xref:System.Windows.Forms.Form.Size%2A> del form.

Nell'esempio di codice riportato di seguito le dimensioni del form sono impostate su 100 × 100 pixel.

```vb
Form1.Size = New System.Drawing.Size(100, 100)
```

```csharp
Form1.Size = new System.Drawing.Size(100, 100);
```

```cpp
Form1->Size = System::Drawing::Size(100, 100);
```

## <a name="change-form-width-and-height-programmatically"></a>Modificare la larghezza e l'altezza del modulo a livello di codice

Una volta definita la proprietà <xref:System.Windows.Forms.Form.Size%2A>, è possibile modificare l'altezza o la larghezza del form usando la proprietà <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.

Nell'esempio di codice riportato di seguito viene illustrato come impostare la larghezza del form su 300 pixel dal bordo sinistro del form, mentre l'altezza rimane costante.

```vb
Form1.Width = 300
```

```csharp
Form1.Width = 300;
```

```cpp
Form1->Width = 300;
```

-oppure-

Modificare la proprietà <xref:System.Drawing.Size.Width%2A> o la proprietà <xref:System.Drawing.Size.Height%2A> impostando la proprietà <xref:System.Windows.Forms.Form.Size%2A>.

Tuttavia, come illustrato nell'esempio di codice riportato di seguito, questo approccio risulta più complesso rispetto alla semplice impostazione delle proprietà <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.

```vb
Form1.Size = New Size(300, Form1.Size.Height)
```

```csharp
Form1.Size = new Size(300, Form1.Size.Height);
```

```cpp
Form1->Size = System::Drawing::Size(300, Form1->Size.Height);
```

## <a name="change-form-size-by-increments-programmatically"></a>Modificare le dimensioni del modulo per incrementi a livello di codice

Per incrementare le dimensioni del form, impostare le proprietà <xref:System.Drawing.Size.Width%2A> o <xref:System.Drawing.Size.Height%2A>.

Nell'esempio di codice riportato di seguito la larghezza del form viene aumentata di 200 pixel rispetto all'impostazione corrente.

```vb
Form1.Width += 200
```

```csharp
Form1.Width += 200;
```

```cpp
Form1->Width += 200;
```

> [!CAUTION]
> Usare sempre la proprietà <xref:System.Drawing.Size.Height%2A> o la proprietà <xref:System.Drawing.Size.Width%2A> per modificare le dimensioni di un form, a meno che le dimensioni di altezza e larghezza non vengano impostate contemporaneamente mediante la proprietà <xref:System.Windows.Forms.Form.Size%2A> in una nuova struttura <xref:System.Drawing.Size>. La proprietà <xref:System.Windows.Forms.Form.Size%2A> restituisce una struttura <xref:System.Drawing.Size>, che è un tipo di valore. Non è possibile assegnare un nuovo valore alla proprietà di un tipo di valore. Di conseguenza, l'esempio di codice riportato di seguito non verrà compilato.

```vb
' NOTE: CODE WILL NOT COMPILE
Dim f As New Form()
f.Size.Width += 100
```

```csharp
// NOTE: CODE WILL NOT COMPILE
Form f = new Form();
f.Size.Width += 100;
```

```cpp
// NOTE: CODE WILL NOT COMPILE
Form^ f = gcnew Form();
f->Size->X += 100;
```

## <a name="see-also"></a>Vedere anche

- [Guida introduttiva a Windows Form](getting-started-with-windows-forms.md)
- [Miglioramento delle applicazioni Windows Form](./advanced/index.md)
