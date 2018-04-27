---
title: "Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)"
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10c6bdf46e351b23705107da3b693531718cfd37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)
È possibile derivare classi Visual Basic da `Public` classi di oggetti COM, anche quelli creati in versioni precedenti di Visual Basic. Le proprietà e metodi delle classi ereditate da oggetti COM possono essere sottoposto a override o sottoposti a overload solo come proprietà e metodi di qualsiasi altra classe di base possono essere sottoposto a override o di overload. Ereditarietà dagli oggetti COM è utile quando si dispone di una libreria di classe esistente che non si desidera ricompilare.  
  
 La procedura seguente viene illustrato come utilizzare Visual Basic 6.0 per creare un oggetto COM che contiene una classe e quindi utilizzarlo come classe base.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Per compilare l'oggetto COM che è utilizzato in questa procedura dettagliata  
  
1.  In Visual Basic 6.0, aprire un nuovo progetto ActiveX DLL. Un progetto denominato `Project1` viene creato. Dispone di una classe denominata `Class1`.  
  
2.  Nel **Esplora progetti**, fare doppio clic su **Project1**, quindi fare clic su **proprietà Project1**. Il **le proprietà del progetto** viene visualizzata la finestra di dialogo.  
  
3.  Nel **generale** scheda della finestra il **le proprietà del progetto** finestra di dialogo, modificare il nome del progetto digitando `ComObject1` nel **nome progetto** campo.  
  
4.  Nel **Esplora progetti**, fare doppio clic su `Class1`, quindi fare clic su **proprietà**. Il **proprietà** verrà visualizzata la finestra per la classe.  
  
5.  Modifica il `Name` proprietà `MathFunctions`.  
  
6.  Nel **Esplora progetti**, fare doppio clic su `MathFunctions`, quindi fare clic su **Visualizza codice**. Il **Editor di codice** viene visualizzato.  
  
7.  Aggiungere una variabile locale per contenere il valore della proprietà:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Aggiungere proprietà `Let` e proprietà `Get` le routine della proprietà:  
  
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
  
10. Creare e registrare l'oggetto COM, fare clic su **Crea ComObject1. dll** sul **File** menu.  
  
    > [!NOTE]
    >  Sebbene sia possibile esporre anche una classe creata con Visual Basic come un oggetto COM, non è un oggetto COM true e non può essere utilizzato in questa procedura dettagliata. Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Assembly di interoperabilità  
 Nella procedura seguente, si creerà un assembly di interoperabilità, che funge da ponte tra il codice non gestito (ad esempio un oggetto COM) e il codice gestito [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] utilizza. L'assembly di interoperabilità che Visual Basic crea gestisce molti dettagli dell'utilizzo di oggetti COM, ad esempio *marshalling di interoperabilità*, il processo di creazione del pacchetto parametri e valori restituiti in dati equivalente tipi quando passano a e dagli oggetti COM. Il riferimento nell'applicazione Visual Basic che punta all'assembly di interoperabilità, non all'oggetto COM.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Per utilizzare un oggetto COM con Visual Basic 2005 e versioni successive  
  
1.  Aprire un nuovo progetto applicazione Windows Visual Basic.  
  
2.  Scegliere **Aggiungi riferimento** dal menu **Progetto**.  
  
     Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.  
  
3.  Nel **COM** scheda, fare doppio clic su `ComObject1` nel **nome componente** elenco e fare clic su **OK**.  
  
4.  Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.  
  
     Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
5.  Nel **modelli** riquadro, fare clic su **classe**.  
  
     Il nome di file predefinito, `Class1.vb`, viene visualizzato nel **nome** campo. Modificare questo campo MathClass e fare clic su **Aggiungi**. Verrà creata una classe denominata `MathClass`e verrà visualizzato il codice.  
  
6.  Aggiungere il codice seguente all'inizio del `MathClass` per ereditare dalla classe COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Eseguire l'overload del metodo pubblico della classe di base aggiungendo il seguente codice al `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Estendere la classe ereditata aggiungendo il seguente codice al `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 La nuova classe eredita le proprietà della classe di base dell'oggetto COM, un metodo di overload e definisce un nuovo metodo per estendere la classe.  
  
#### <a name="to-test-the-inherited-class"></a>Per testare la classe ereditata  
  
1.  Aggiungere un pulsante al form di avvio e quindi fare doppio clic per visualizzare il codice.  
  
2.  Il pulsante `Click` routine del gestore eventi, aggiungere il codice seguente per creare un'istanza di `MathClass` e chiamare i metodi di overload:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Premere F5 per eseguire il progetto.  
  
 Quando si fa clic sul pulsante nel form, il `AddNumbers` metodo viene chiamato con `Short` numeri, del tipo di dati e Visual Basic viene scelto il metodo appropriato dalla classe di base. La seconda chiamata a `AddNumbers` viene indirizzata al metodo di overload da `MathClass`. La terza chiamata richiama il `SubtractNumbers` metodo, che estende la classe. La proprietà nella classe base è impostata, e viene visualizzato il valore.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Si può notare che il metodo di overload `AddNumbers` funzione sembra avere dati dello stesso tipo del metodo ereditato dalla classe di base dell'oggetto COM. Infatti, gli argomenti e parametri del metodo della classe base sono definiti come interi a 16 bit in Visual Basic 6.0, ma sono esposti come interi a 16 bit di tipo `Short` nelle versioni successive di Visual Basic. La nuova funzione accetta interi a 32 bit e la funzione di classe di base di overload.  
  
 Quando si lavora con gli oggetti COM, verificare che le dimensioni e tipi di dati dei parametri. Ad esempio, quando si utilizza un oggetto COM che accetta un oggetto raccolta di Visual Basic 6.0 come argomento, è possibile fornire una raccolta di una versione successiva di Visual Basic.  
  
 Proprietà e metodi ereditati dalle classi COM possono essere sottoposto a override, vale a dire che è possibile dichiarare una proprietà locale o un metodo che sostituisce una proprietà o un metodo ereditato da una classe COM di base. Le regole per eseguire l'override delle proprietà ereditate COM sono simili alle regole per eseguire l'override di altre proprietà e metodi con le eccezioni seguenti:  
  
-   Se si esegue l'override di qualsiasi proprietà o un metodo ereditato da una classe COM, è necessario eseguire l'override di tutte le altre proprietà ereditate e i metodi.  
  
-   Le proprietà che utilizzano `ByRef` parametri non possono essere sottoposto a override.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
