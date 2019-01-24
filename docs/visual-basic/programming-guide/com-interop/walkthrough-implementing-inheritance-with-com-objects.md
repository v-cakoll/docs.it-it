---
title: "Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: e99deb2ea5e8acd5e1e07adffe29d35e2624b27e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648206"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)
È possibile derivare classi Visual Basic da `Public` classi di oggetti COM, anche quelli creati in versioni precedenti di Visual Basic. Le proprietà e metodi delle classi ereditate dagli oggetti COM possono essere sottoposto a override o overload solo come proprietà e metodi di qualsiasi altra classe base possono essere sottoposto a override o overload. Ereditarietà dagli oggetti COM è utile quando si dispone di una libreria di classi esistenti che non si desidera ricompilare.  
  
 La procedura seguente viene illustrato come utilizzare Visual Basic 6.0 per creare un oggetto COM che contiene una classe e quindi usarla come una classe di base.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Per creare l'oggetto COM che viene usato in questa procedura dettagliata  
  
1.  In Visual Basic 6.0, aprire un nuovo progetto di DLL ActiveX. Un progetto denominato `Project1` viene creato. Dispone di una classe denominata `Class1`.  
  
2.  Nel **Esplora progetti**, fare doppio clic su **Project1**, quindi fare clic su **Project1 proprietà**. Il **proprietà del progetto** verrà visualizzata la finestra di dialogo.  
  
3.  Nel **generale** scheda della finestra di **le proprietà del progetto** finestra di dialogo, modificare il nome del progetto digitando `ComObject1` nel **nome progetto** campo.  
  
4.  Nel **Esplora progetti**, fare doppio clic su `Class1`, quindi fare clic su **proprietà**. Il **proprietà** viene visualizzata la finestra per la classe.  
  
5.  Modifica il `Name` proprietà `MathFunctions`.  
  
6.  Nel **Esplora progetti**, fare doppio clic su `MathFunctions`, quindi fare clic su **Visualizza codice**. Il **Editor di codice** viene visualizzato.  
  
7.  Aggiungere una variabile locale per contenere il valore della proprietà:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Aggiungi proprietà `Let` e la proprietà `Get` routine delle proprietà:  
  
    ```  
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
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. Creare e registrare l'oggetto COM facendo **Crea ComObject1. dll** nel **File** menu.  
  
    > [!NOTE]
    >  Sebbene sia possibile esporre anche una classe creata con Visual Basic come oggetto COM, non è un vero oggetto COM e non può essere usato in questa procedura dettagliata. Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Assembly di interoperabilità  
 Nella procedura seguente, si creerà un assembly di interoperabilità, che funge da ponte tra il codice non gestito (ad esempio, un oggetto COM) e il codice gestito che Usa Visual Studio. L'assembly di interoperabilità che Visual Basic crea gestisce molti dettagli dell'utilizzo di oggetti COM, ad esempio *marshalling di interoperabilità*, il processo di creazione dei pacchetti parametri e valori restituiti in dati equivalenti i tipi di esempio su cui spostarsi e dagli oggetti COM. Il riferimento nell'applicazione Visual Basic che punta all'assembly di interoperabilità, non l'oggetto COM effettivo.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Usare un oggetto COM con Visual Basic 2005 e versioni successive  
  
1.  Aprire un nuovo progetto Applicazione Windows in Visual Basic.  
  
2.  Scegliere **Aggiungi riferimento** dal menu **Progetto**.  
  
     Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.  
  
3.  Nel **COM** scheda, fare doppio clic su `ComObject1` nel **nome componente** elenco e fare clic su **OK**.  
  
4.  Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.  
  
     Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
5.  Nel **modelli** riquadro, fare clic su **classe**.  
  
     Il nome file predefinito, `Class1.vb`, viene visualizzato nei **nome** campo. Modificare questo campo MathClass e fare clic su **Add**. Verrà creata una classe denominata `MathClass`e verrà visualizzato il codice.  
  
6.  Aggiungere il codice seguente all'inizio del `MathClass` ereditare dalla classe COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Overload del metodo pubblico della classe di base aggiungendo il codice seguente al `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Estendere la classe ereditata aggiungendo il codice seguente al `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 La nuova classe eredita le proprietà della classe di base dell'oggetto COM, un metodo di overload e definisce un nuovo metodo per estendere la classe.  
  
#### <a name="to-test-the-inherited-class"></a>Per eseguire il test sulla classe ereditata  
  
1.  Aggiungere un pulsante al form di avvio e quindi fare doppio clic per visualizzare il codice.  
  
2.  Nel pulsante `Click` routine del gestore eventi, aggiungere il codice seguente per creare un'istanza di `MathClass` e chiamare i metodi di overload:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Eseguire il progetto premendo F5.  
  
 Quando si fa clic sul pulsante nel form, il `AddNumbers` viene chiamato prima di tutto con `Short` numeri, tipo di dati e Visual Basic sceglie il metodo appropriato della classe base. La seconda chiamata a `AddNumbers` viene indirizzata al metodo di overload da `MathClass`. La terza chiamata richiama il `SubtractNumbers` metodo, che estende la classe. La proprietà nella classe di base è impostata e viene visualizzato il valore.  
  
## <a name="next-steps"></a>Passaggi successivi  
 È possibile aver notato che l'overload `AddNumbers` funzione sembra avere gli stessi dati di tipo del metodo ereditato dalla classe di base dell'oggetto COM. Infatti, gli argomenti e parametri del metodo della classe base sono definiti come numeri interi a 16 bit in Visual Basic 6.0, ma sono esposte come interi a 16 bit di tipo `Short` nelle versioni più recenti di Visual Basic. La nuova funzione accetta numeri interi a 32 bit e gli overload di funzione di classe base.  
  
 Quando si usano oggetti COM, assicurarsi di verificare le dimensioni e tipi di dati dei parametri. Ad esempio, quando si usa un oggetto COM che accetta come argomento un oggetto raccolta di Visual Basic 6.0, è possibile fornire un insieme di una versione successiva di Visual Basic.  
  
 Le proprietà e metodi ereditati da classi COM a cui possono essere sostituiti, vale a dire che è possibile dichiarare una proprietà locale o un metodo che sostituisce una proprietà o metodo ereditato da una classe COM di base. Le regole per eseguire l'override delle proprietà ereditate COM sono simili alle regole per eseguire l'override di altre proprietà e metodi con le eccezioni seguenti:  
  
-   Se si esegue l'override di proprietà o metodi ereditati da una classe COM, è necessario eseguire l'override di tutte le altre proprietà ereditate e i metodi.  
  
-   Proprietà che utilizzano `ByRef` parametri non possono essere sottoposto a override.  
  
## <a name="see-also"></a>Vedere anche
- [Interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
