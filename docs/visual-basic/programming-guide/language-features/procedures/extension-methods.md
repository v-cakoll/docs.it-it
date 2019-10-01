---
title: Metodi di estensione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: b5ad066fe9ec40d715702ed99537f45b21c558cf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701049"
---
# <a name="extension-methods-visual-basic"></a>Metodi di estensione (Visual Basic)

I metodi di estensione consentono agli sviluppatori di aggiungere funzionalità personalizzate ai tipi di dati già definiti senza creare un nuovo tipo derivato. I metodi di estensione consentono di scrivere un metodo che può essere chiamato come se fosse un metodo di istanza del tipo esistente.
  
## <a name="remarks"></a>Note

Un metodo di estensione può essere solo una routine `Sub` o una procedura `Function`. Non è possibile definire una proprietà, un campo o un evento di estensione. Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension>` dallo spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> e devono essere definiti in un [modulo](../../../language-reference/statements/module-statement.md). Se un metodo di estensione viene definito all'esterno di un modulo, il Visual Basic compilatore genera l'errore [BC36551](../../../misc/bc36551.md), "i metodi di estensione possono essere definiti solo nei moduli".

Il primo parametro di una definizione di metodo di estensione specifica il tipo di dati che il metodo estende. Quando viene eseguito il metodo, il primo parametro viene associato all'istanza del tipo di dati che richiama il metodo.

L'attributo `Extension` può essere applicato solo a una Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md)o [`Function`](../../../language-reference/statements/function-statement.md). Se lo si applica a un `Class` o a un `Structure`, il compilatore Visual Basic genera l'errore [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md)"l'attributo" extension "può essere applicato solo alle dichiarazioni ' Module ',' Sub ' o ' Function '.

## <a name="example"></a>Esempio

Nell'esempio seguente viene definita un'estensione `Print` per il tipo di dati <xref:System.String>. Il metodo usa `Console.WriteLine` per visualizzare una stringa. Il parametro del metodo `Print`, `aString`, stabilisce che il metodo estende la classe <xref:System.String>.
  
[!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]

Si noti che la definizione del metodo di estensione è contrassegnata con l'attributo di estensione `<Extension()>`. Contrassegnare il modulo in cui è definito il metodo è facoltativo, ma ogni metodo di estensione deve essere contrassegnato. per accedere all'attributo di estensione, è necessario importare <xref:System.Runtime.CompilerServices>.

I metodi di estensione possono essere dichiarati solo all'interno di moduli. In genere, il modulo in cui è definito un metodo di estensione non corrisponde a quello in cui viene chiamato. Al contrario, il modulo che contiene il metodo di estensione viene importato, se necessario, per riportarlo nell'ambito. Quando il modulo che contiene `Print` rientra nell'ambito, il metodo può essere chiamato come se fosse un metodo di istanza normale che non accetta argomenti, ad esempio `ToUpper`:

[!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]

L'esempio successivo, `PrintAndPunctuate`, è anche un'estensione di <xref:System.String>, questa volta definito con due parametri. Il primo parametro, `aString`, stabilisce che il metodo di estensione estende <xref:System.String>. Il secondo parametro, `punc`, deve essere una stringa di segni di punteggiatura che viene passata come argomento quando viene chiamato il metodo. Il metodo Visualizza la stringa seguita dai segni di punteggiatura.

[!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]

Il metodo viene chiamato inviando in un argomento stringa per `punc`: `example.PrintAndPunctuate(".")`

Nell'esempio seguente vengono illustrati `Print` e `PrintAndPunctuate` definiti e chiamati. <xref:System.Runtime.CompilerServices> viene importato nel modulo di definizione per consentire l'accesso all'attributo di estensione.


```vb
Imports System.Runtime.CompilerServices

Module StringExtensions

    <Extension()>
    Public Sub Print(aString As String)
        Console.WriteLine(aString)
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module
```

Successivamente, i metodi di estensione vengono inseriti nell'ambito e chiamati:

```vb
Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example As String = "Example string"
        example.Print()

        example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")
    End Sub
End Module
```

Tutto ciò che è necessario per poter eseguire questi o metodi di estensione simili è che si trovino nell'ambito. Se il modulo che contiene un metodo di estensione è nell'ambito, è visibile in IntelliSense e può essere chiamato come se fosse un metodo di istanza comune.

Si noti che quando vengono richiamati i metodi, per il primo parametro non viene inviato alcun argomento. Il parametro `aString` nelle definizioni di metodo precedenti è associato a `example`, l'istanza di `String` che li chiama. Il compilatore utilizzerà `example` come argomento inviato al primo parametro.

Se viene chiamato un metodo di estensione per un oggetto impostato su `Nothing`, viene eseguito il metodo di estensione. Questa operazione non si applica ai metodi di istanza ordinari. È possibile verificare in modo esplicito `Nothing` nel metodo di estensione.

## <a name="types-that-can-be-extended"></a>Tipi che possono essere estesi

È possibile definire un metodo di estensione per la maggior parte dei tipi che possono essere rappresentati in un elenco di parametri Visual Basic, inclusi i seguenti:

- Classi (tipi di riferimento)
- Strutture (tipi di valore)
- Interfacce
- Delegati
- Argomenti ByRef e ByVal
- Parametri del metodo generico
- Matrici

Poiché il primo parametro specifica il tipo di dati che il metodo di estensione estende, è obbligatorio e non può essere facoltativo. Per questo motivo, i parametri `Optional` e i parametri `ParamArray` non possono essere il primo parametro nell'elenco di parametri.

I metodi di estensione non vengono considerati nell'associazione tardiva. Nell'esempio seguente l'istruzione `anObject.PrintMe()` genera un'eccezione <xref:System.MissingMemberException>, ovvero la stessa eccezione che si verifica se è stata eliminata la seconda definizione del metodo di estensione `PrintMe`.

[!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]

## <a name="best-practices"></a>Procedure consigliate

I metodi di estensione forniscono un metodo pratico e potente per estendere un tipo esistente. Tuttavia, per usarli correttamente, è necessario prendere in considerazione alcuni aspetti. Queste considerazioni si applicano principalmente agli autori di librerie di classi, ma potrebbero influire su qualsiasi applicazione che utilizza i metodi di estensione.

In generale, i metodi di estensione aggiunti ai tipi di cui non si è proprietari sono più vulnerabili dei metodi di estensione aggiunti ai tipi che si controllano. Nelle classi che non si possiede possono verificarsi numerose operazioni che possono interferire con i metodi di estensione.

- Se esiste un membro di istanza accessibile che dispone di una firma compatibile con gli argomenti nell'istruzione chiamante, senza conversioni verso un tipo di argomento più piccolo richiesto dall'argomento al parametro, il metodo di istanza verrà utilizzato in modo preferenziale per qualsiasi metodo di estensione. Pertanto, se un metodo di istanza appropriato viene aggiunto a una classe in un determinato punto, un membro di estensione esistente su cui si basa la dipendenza potrebbe diventare inaccessibile.

- L'autore di un metodo di estensione non può impedire ad altri programmatori di scrivere metodi di estensione in conflitto che possono avere la precedenza sull'estensione originale.

- È possibile migliorare la robustezza inserendo i metodi di estensione nel relativo spazio dei nomi. I consumer della libreria possono quindi includere uno spazio dei nomi o escluderlo oppure selezionare tra gli spazi dei nomi, separatamente dal resto della libreria.

- Potrebbe essere più sicuro estendere le interfacce anziché estendere le classi, specialmente se non si è proprietari dell'interfaccia o della classe. Una modifica in un'interfaccia influiscono su ogni classe che la implementa. Pertanto, l'autore potrebbe avere meno probabilità di aggiungere o modificare i metodi in un'interfaccia. Tuttavia, se una classe implementa due interfacce con metodi di estensione con la stessa firma, il metodo di estensione non è visibile.

- Estendere il tipo più specifico possibile. In una gerarchia di tipi, se si seleziona un tipo da cui derivano molti altri tipi, esistono livelli di possibilità per l'introduzione di metodi di istanza o altri metodi di estensione che potrebbero interferire con l'utente.

## <a name="extension-methods-instance-methods-and-properties"></a>Metodi di estensione, metodi di istanza e proprietà

Quando un metodo di istanza in ambito dispone di una firma compatibile con gli argomenti di un'istruzione chiamante, il metodo di istanza viene scelto in preferenza rispetto a qualsiasi metodo di estensione. Il metodo di istanza ha la precedenza anche se il metodo di estensione è una corrispondenza migliore. Nell'esempio seguente `ExampleClass` contiene un metodo di istanza denominato `ExampleMethod` con un parametro di tipo `Integer`. Il metodo di estensione `ExampleMethod` estende `ExampleClass` e ha un parametro di tipo `Long`.

[!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]

La prima chiamata a `ExampleMethod` nel codice seguente chiama il metodo di estensione, perché `arg1` è `Long` ed è compatibile solo con il parametro `Long` nel metodo di estensione. La seconda chiamata a `ExampleMethod` ha un argomento `Integer`, `arg2`, e chiama il metodo di istanza.

[!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]

Invertire ora i tipi di dati dei parametri nei due metodi:

[!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]

Questa volta il codice in `Main` chiama il metodo di istanza entrambe le volte. Ciò è dovuto al fatto che sia `arg1` che `arg2` hanno una conversione verso un tipo di `Long` e il metodo di istanza ha la precedenza sul metodo di estensione in entrambi i casi.

[!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]

Pertanto, un metodo di estensione non può sostituire un metodo di istanza esistente. Tuttavia, quando un metodo di estensione ha lo stesso nome di un metodo di istanza ma le firme non sono in conflitto, è possibile accedere a entrambi i metodi. Se, ad esempio, la classe `ExampleClass` contiene un metodo denominato `ExampleMethod` che non accetta argomenti, sono consentiti metodi di estensione con lo stesso nome ma firme diverse, come illustrato nel codice seguente.

[!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]

L'output di questo codice è il seguente:

```console
Extension method
Instance method
```

La situazione è più semplice con le proprietà: se un metodo di estensione ha lo stesso nome di una proprietà della classe che estende, il metodo di estensione non è visibile e non è possibile accedervi.

## <a name="extension-method-precedence"></a>Precedenza metodo di estensione

Quando due metodi di estensione con firme identiche si trovano nell'ambito e sono accessibili, viene richiamato quello con precedenza più alta. La precedenza di un metodo di estensione è basata sul meccanismo utilizzato per portare il metodo nell'ambito. Nell'elenco seguente viene illustrata la gerarchia di precedenza, dal più alto al più basso.

1. Metodi di estensione definiti all'interno del modulo corrente.

2. I metodi di estensione definiti nei tipi di dati nello spazio dei nomi corrente o in uno qualsiasi dei relativi elementi padre, con spazi dei nomi figlio con precedenza maggiore rispetto agli spazi dei nomi padre.

3. Metodi di estensione definiti in qualsiasi importazione di tipi nel file corrente.

4. Metodi di estensione definiti in qualsiasi importazione di spazi dei nomi nel file corrente.

5. Metodi di estensione definiti in qualsiasi importazione di tipi a livello di progetto.

6. Metodi di estensione definiti in qualsiasi importazione di spazi dei nomi a livello di progetto.

Se la precedenza non risolve l'ambiguità, è possibile usare il nome completo per specificare il metodo che si sta chiamando. Se il metodo `Print` nell'esempio precedente è definito in un modulo denominato `StringExtensions`, il nome completo è `StringExtensions.Print(example)` anziché `example.Print()`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Metodi di estensione](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Istruzione Module](../../../language-reference/statements/module-statement.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Parametri facoltativi](optional-parameters.md)
- [Matrici di parametri](parameter-arrays.md)
- [Panoramica degli attributi](../../concepts/attributes/index.md)
- [Ambito in Visual Basic](../declared-elements/scope.md)
