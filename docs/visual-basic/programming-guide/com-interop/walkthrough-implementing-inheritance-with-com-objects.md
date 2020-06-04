---
title: "Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM"
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: bdb891e1a150f0d7b79aefcc3db1f18dc8e84be4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396727"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)

È possibile derivare Visual Basic classi da `Public` classi negli oggetti com, anche quelle create nelle versioni precedenti di Visual Basic. Le proprietà e i metodi delle classi ereditate dagli oggetti COM possono essere sottoposti a override o sottoposti a overload come le proprietà e i metodi di qualsiasi altra classe di base possono essere sostituiti o sottoposti a overload. L'ereditarietà dagli oggetti COM è utile quando si dispone di una libreria di classi esistente che non si desidera ricompilare.

Nella procedura seguente viene illustrato come utilizzare Visual Basic 6,0 per creare un oggetto COM contenente una classe e quindi utilizzarlo come classe base.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Per compilare l'oggetto COM utilizzato in questa procedura dettagliata

1. In Visual Basic 6,0 aprire un nuovo progetto di DLL ActiveX. Viene creato un progetto denominato `Project1` . Dispone di una classe denominata `Class1` .

2. In **Esplora progetti**fare clic con il pulsante destro del mouse su **Project1**e quindi scegliere **Proprietà Project1**. Verrà visualizzata la finestra di dialogo **Proprietà progetto** .

3. Nella scheda **generale** della finestra di dialogo **Proprietà progetto** modificare il nome del progetto digitando `ComObject1` nel campo **nome progetto** .

4. In **Esplora progetti**fare clic con il pulsante destro del mouse su `Class1` , quindi scegliere **proprietà**. Viene visualizzata la finestra **Proprietà** per la classe.

5. Modificare la `Name` Proprietà in `MathFunctions` .

6. In **Esplora progetti**fare clic con il pulsante destro del mouse su `MathFunctions` , quindi scegliere **Visualizza codice**. Viene visualizzato l' **editor di codice** .

7. Aggiungere una variabile locale per conservare il valore della proprietà:

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. Aggiungere `Let` routine di proprietà e proprietà `Get` :

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. Aggiungere una funzione:

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. Creare e registrare l'oggetto COM scegliendo **make ComObject1. dll** dal menu **file** .

    > [!NOTE]
    > Sebbene sia anche possibile esporre una classe creata con Visual Basic come oggetto COM, non è un vero oggetto COM e non può essere utilizzata in questa procedura dettagliata. Per informazioni dettagliate, vedere [interoperabilità com nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md).

## <a name="interop-assemblies"></a>Assembly di interoperabilità

Nella procedura seguente verrà creato un assembly di interoperabilità, che funge da Bridge tra codice non gestito (ad esempio un oggetto COM) e il codice gestito utilizzato da Visual Studio. L'assembly di interoperabilità creato da Visual Basic gestisce molti dettagli sull'utilizzo di oggetti COM, ad esempio il *marshalling di interoperabilità*, il processo di creazione del pacchetto di parametri e la restituzione di valori in tipi di dati equivalenti durante il passaggio da e verso oggetti com. Il riferimento nell'applicazione Visual Basic punta all'assembly di interoperabilità, non all'oggetto COM effettivo.

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Per usare un oggetto COM con Visual Basic 2005 e versioni successive

1. Aprire un nuovo progetto Applicazione Windows in Visual Basic.

2. Scegliere **Aggiungi riferimento** dal menu **Progetto**.

     Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.

3. Nella scheda **com** fare doppio clic `ComObject1` nell'elenco **nome componente** e fare clic su **OK**.

4. Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.

     La finestra di dialogo **Aggiungi nuovo elemento** viene visualizzata.

5. Nel riquadro **modelli** fare clic su **classe**.

     Il nome file predefinito, `Class1.vb` , viene visualizzato nel campo **nome** . Modificare questo campo in MathClass. vb e fare clic su **Aggiungi**. Viene creata una classe denominata `MathClass` e viene visualizzato il relativo codice.

6. Aggiungere il codice seguente all'inizio di `MathClass` per ereditare dalla classe com.

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. Eseguire l'overload del metodo pubblico della classe base aggiungendo il codice seguente a `MathClass` :

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. Estendere la classe ereditata aggiungendo il codice seguente a `MathClass` :

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

La nuova classe eredita le proprietà della classe di base nell'oggetto COM, sovraccarica un metodo e definisce un nuovo metodo per estendere la classe.

### <a name="to-test-the-inherited-class"></a>Per testare la classe ereditata

1. Aggiungere un pulsante al form di avvio e quindi fare doppio clic su di esso per visualizzarne il codice.

2. Nella procedura relativa al `Click` gestore eventi del pulsante aggiungere il codice seguente per creare un'istanza di `MathClass` e chiamare i metodi di overload:

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. Eseguire il progetto premendo F5.

Quando si fa clic sul pulsante nel form, il `AddNumbers` metodo viene chiamato prima con i `Short` numeri dei tipi di dati e Visual Basic sceglie il metodo appropriato dalla classe di base. La seconda chiamata a `AddNumbers` viene indirizzata al metodo di overload da `MathClass` . La terza chiamata chiama il `SubtractNumbers` metodo, che estende la classe. Viene impostata la proprietà nella classe di base e viene visualizzato il valore.

## <a name="next-steps"></a>Passaggi successivi

Si può notare che la `AddNumbers` funzione in overload sembra avere lo stesso tipo di dati del metodo ereditato dalla classe di base dell'oggetto com. Ciò è dovuto al fatto che gli argomenti e i parametri del metodo della classe base sono definiti come interi a 16 bit in Visual Basic 6,0, ma vengono esposti come interi a 16 bit di tipo `Short` nelle versioni successive di Visual Basic. La nuova funzione accetta interi a 32 bit e sovraccarica la funzione della classe di base.

Quando si utilizzano gli oggetti COM, assicurarsi di verificare le dimensioni e i tipi di dati dei parametri. Ad esempio, quando si usa un oggetto COM che accetta un oggetto raccolta Visual Basic 6,0 come argomento, non è possibile fornire una raccolta da una versione successiva di Visual Basic.

È possibile eseguire l'override delle proprietà e dei metodi ereditati dalle classi COM, vale a dire che è possibile dichiarare una proprietà o un metodo locale che sostituisce una proprietà o un metodo ereditato da una classe COM di base. Le regole per l'override delle proprietà COM ereditate sono simili a quelle per l'override di altre proprietà e metodi con le eccezioni seguenti:

- Se si esegue l'override di qualsiasi proprietà o metodo ereditato da una classe COM, è necessario eseguire l'override di tutte le altre proprietà e metodi ereditati.

- Non è possibile eseguire l'override delle proprietà che usano `ByRef` parametri.

## <a name="see-also"></a>Vedere anche

- [Interoperabilità COM nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md)
- [Inherits Statement](../../language-reference/statements/inherits-statement.md)
- [Tipo di dati Short](../../language-reference/data-types/short-data-type.md)
