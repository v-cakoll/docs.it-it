---
title: 'Procedura: inserire virgolette in una stringa'
description: Informazioni su come inserire le virgolette in una stringa di testo. Viene inoltre illustrato come utilizzare il campo quote come costante.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 08a3e2ab5662cbbf7825890ab430fddcd7b4a9ce
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903623"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Procedura: inserire virgolette in una stringa (Windows Form)
In alcuni casi è possibile racchiudere tra virgolette (" ") una stringa di testo. Ad esempio:  
  
 Ha detto, "Meritate un treat!"  
  
 In alternativa, è anche possibile usare il <xref:Microsoft.VisualBasic.ControlChars.Quote> campo come costante.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>Per inserire le virgolette in una stringa nel codice  
  
1. In Visual Basic inserire due virgolette in una riga come virgolette incorporate. In Visual C# e Visual C++ Inserire la sequenza di escape \\ "come virgolette incorporate. Ad esempio, per creare la stringa precedente, usare il codice seguente.  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     -oppure-  
  
2. Inserire il carattere ASCII o Unicode per una virgoletta. In Visual Basic usare il carattere ASCII (34). In Visual C# usare il carattere Unicode (\u0022).  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    > In questo esempio, non è possibile usare \u0022 perché non è possibile usare un nome di carattere universale che indica un carattere nel set di caratteri di base. In caso contrario, si otterrebbe C3851. Per altre informazioni, vedere l'[L'errore del compilatore C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).  
  
     -oppure-  
  
3. È anche possibile definire una costante per il carattere e usarlo se necessario.  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo Password con il controllo TextBox Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo in sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: selezionare testo nel controllo TextBox Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: visualizzare più righe nel controllo TextBox Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
