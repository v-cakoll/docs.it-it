---
title: Metodi di estensione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: aca8f18c4bc53318792a119617b1ca0d6c4cc32e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822076"
---
# <a name="extension-methods-visual-basic"></a>Metodi di estensione (Visual Basic)
I metodi di estensione consentono agli sviluppatori di aggiungere funzionalità personalizzate ai tipi di dati che sono già definiti senza creare un nuovo tipo derivato. I metodi di estensione consentono di scrivere un metodo che può essere chiamato come se fosse un metodo di istanza del tipo esistente.  
  
## <a name="remarks"></a>Note  
 Un metodo di estensione può essere solo un `Sub` routine o un `Function` procedure. È possibile definire una proprietà di estensione, un campo o un evento. Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension()>` dal <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> dello spazio dei nomi.  
  
 Il primo parametro in una definizione di metodo di estensione specifica quale tipo di dati esteso dal metodo. Quando il metodo viene eseguito, il primo parametro è associato all'istanza del tipo di dati che richiama il metodo.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 L'esempio seguente definisce una `Print` estensione per il <xref:System.String> tipo di dati. Il metodo Usa `Console.WriteLine` per visualizzare una stringa. Il parametro del `Print` metodo `aString`, stabilisce che il metodo estende il <xref:System.String> classe.  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 Si noti che la definizione di metodo di estensione è contrassegnata con l'attributo di estensione `<Extension()>`. Il contrassegno del modulo in cui è definito il metodo è facoltativo, ma ogni metodo di estensione deve essere contrassegnato. <xref:System.Runtime.CompilerServices> deve essere importato per accedere all'attributo di estensione.  
  
 I metodi di estensione possono essere dichiarati solo all'interno dei moduli. Il modulo in cui è definito un metodo di estensione non è in genere, il modulo stesso di quello in cui viene chiamato. Al contrario, viene importato il modulo che contiene il metodo di estensione, se deve essere, per portarlo nell'ambito. Dopo il modulo che contiene `Print` è incluso nell'ambito, il metodo può essere chiamato come se fosse un metodo di istanza comune che non accetta argomenti, ad esempio `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 L'esempio successivo `PrintAndPunctuate`, è anche un'estensione <xref:System.String>, questa volta definito con due parametri. Il primo parametro, `aString`, stabilisce che il metodo di estensione estende <xref:System.String>. Il secondo parametro, `punc`, deve essere una stringa di segni di punteggiatura che viene passata come argomento quando viene chiamato il metodo. Il metodo visualizza la stringa seguita dai segni di punteggiatura.  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 Il metodo viene chiamato inviando un argomento stringa per `punc`: `example.PrintAndPunctuate(".")`  
  
 L'esempio seguente illustra `Print` e `PrintAndPunctuate` definizione e la chiamata. <xref:System.Runtime.CompilerServices> viene importato nel modulo della definizione per consentire l'accesso all'attributo di estensione.  
  
### <a name="code"></a>Codice  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 Successivamente, i metodi di estensione vengono inseriti nell'ambito e chiamati.  
  
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
  
### <a name="comments"></a>Commenti  
 Tutto ciò che è necessario essere in grado di eseguire questi passaggi o metodi di estensione simili è che si trovino nell'ambito. Se il modulo che contiene un metodo di estensione è nell'ambito, è visibile in IntelliSense e può essere chiamato come se fosse un metodo di istanza ordinari.  
  
 Si noti che quando vengono richiamati i metodi, viene inviato alcun argomento per il primo parametro. Parametro `aString` nel precedente metodo definizioni è associato a `example`, l'istanza di `String` che li chiama. Il compilatore userà `example` come argomento inviato al primo parametro.  
  
 Se viene chiamato un metodo di estensione per un oggetto che è impostato su `Nothing`, viene eseguito il metodo di estensione. Ciò non si applica ai metodi di istanza comune. È possibile controllare in modo esplicito per `Nothing` nel metodo di estensione.  
  
## <a name="types-that-can-be-extended"></a>Tipi che possono essere estese  
 È possibile definire un metodo di estensione nella maggior parte dei tipi che possono essere rappresentati in un elenco di parametri di Visual Basic, inclusi i seguenti:  
  
-   Classi (tipi riferimento)  
  
-   Strutture (tipi di valore)  
  
-   Interfacce  
  
-   Delegati  
  
-   Argomenti ByRef e ByVal  
  
-   Parametri di metodo generico  
  
-   Matrici  
  
 Poiché il primo parametro specifica il tipo di dati esteso dal metodo di estensione, è obbligatorio e non può essere facoltativo. Per questo motivo `Optional` parametri e `ParamArray` parametri non possono essere il primo parametro nell'elenco dei parametri.  
  
 I metodi di estensione non sono considerati nell'associazione tardiva. Nell'esempio seguente, l'istruzione `anObject.PrintMe()` genera una <xref:System.MissingMemberException> eccezione, la stessa eccezione sarebbe visualizzata se il secondo `PrintMe` definizione di metodo di estensione sono stati eliminati.  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a>Suggerimenti  
 I metodi di estensione forniscono un modo pratico e potente per estendere un tipo esistente. Tuttavia, per poterli utilizzare correttamente, esistono alcuni aspetti da considerare. Queste considerazioni si applicano principalmente gli autori delle librerie di classi, ma che potrebbero influire su qualsiasi applicazione che usa i metodi di estensione.  
  
 In generale, i metodi di estensione aggiunti ai tipi che non si possiede sono più vulnerabili dei metodi di estensione aggiunti ai tipi di cui si controllano. Può verificarsi una serie di operazioni nelle classi non si è proprietari che possono interferire con i metodi di estensione.  
  
-   Se è presente alcun membro di istanza accessibile ha una firma compatibile con gli argomenti dell'istruzione chiamante, con nessuna conversione narrowing richiesto dall'argomento al parametro, verrà utilizzato il metodo di istanza preferenza rispetto a qualsiasi metodo di estensione. Pertanto, se un metodo di istanza appropriato viene aggiunto a una classe a un certo punto, un membro di estensione esistente che affidano potrebbe diventare inaccessibile.  
  
-   L'autore di un metodo di estensione non è possibile impedire agli altri programmatori di scrivere metodi di estensione in conflitto che possono avere la precedenza sull'estensione originale.  
  
-   È possibile migliorare la robustezza inserendo i metodi di estensione nel rispettivo spazio dei nomi. La libreria può quindi includere uno spazio dei nomi o escluderlo oppure effettuare una selezione tra gli spazi dei nomi, separatamente dal resto della libreria.  
  
-   Potrebbe essere più sicuro estendere le interfacce di cui è possibile estendere le classi, soprattutto se non si possiede l'interfaccia o classe. Una modifica in un'interfaccia influisce su ogni classe che lo implementa. Pertanto, l'autore potrebbe essere meno probabile che aggiungere o modificare i metodi in un'interfaccia. Tuttavia, se una classe implementa due interfacce con metodi di estensione con la stessa firma, nessuno dei due metodi di estensione sono visibili.  
  
-   Estendere il tipo più specifico, che è possibile. In una gerarchia di tipi, se si seleziona un tipo dal quale sono derivati molti altri tipi, sono presenti livelli di possibilità per l'introduzione di metodi di istanza o altri metodi di estensione che potrebbero interferire con i propri.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>I metodi di estensione, metodi di istanza e proprietà  
 Quando un metodo di istanza inclusi nell'ambito ha una firma compatibile con gli argomenti di un'istruzione di chiamata, il metodo di istanza viene preferito a qualsiasi metodo di estensione. Il metodo di istanza ha la precedenza anche se il metodo di estensione è una corrispondenza migliore. Nell'esempio riportato di seguito `ExampleClass` contiene un metodo di istanza denominato `ExampleMethod` che ha un parametro di tipo `Integer`. Metodo di estensione `ExampleMethod` estende `ExampleClass`, e ha un parametro di tipo `Long`.  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 La prima chiamata a `ExampleMethod` nel codice seguente chiama il metodo di estensione, in quanto `arg1` viene `Long` ed è compatibile solo con il `Long` parametro nel metodo di estensione. La seconda chiamata a `ExampleMethod` ha un `Integer` argomento, `arg2`, e chiama il metodo di istanza.  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 Invertire ora i tipi di dati dei parametri nei due metodi:  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 Questa volta il codice in `Main` chiama il metodo di istanza due volte. Infatti, entrambi `arg1` e `arg2` hanno una conversione widening `Long`, e il metodo di istanza ha la precedenza sul metodo di estensione in entrambi i casi.  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 Pertanto, un metodo di estensione non è possibile sostituire un metodo di istanza esistenti. Tuttavia, quando un metodo di estensione ha lo stesso nome di un metodo di istanza ma le firme non sono in conflitto, entrambi i metodi accessibili. Ad esempio, se classe `ExampleClass` contiene un metodo denominato `ExampleMethod` che non accetta argomenti, i metodi di estensione con lo stesso nome ma sono consentite firme diverse, come illustrato nel codice seguente.  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 Come indicato di seguito è riportato l'output da questo codice:  
  
 `Extension method`  
  
 `Instance method`  
  
 La situazione è più semplice con proprietà: se un metodo di estensione ha lo stesso nome come una proprietà di classe che estende, il metodo di estensione non è visibile e non è accessibile.  
  
## <a name="extension-method-precedence"></a>Precedenza nei metodi di estensione  
 Quando due metodi di estensione che hanno firme identiche sono nell'ambito e accessibili, verrà richiamato quello con priorità più alta. Precedenza di un metodo di estensione è basata sul meccanismo utilizzato per portare il metodo nell'ambito. Nell'elenco seguente mostra la gerarchia di precedenza, dal maggiore al minore.  
  
1.  Metodi di estensione definiti all'interno del modulo corrente.  
  
2.  Metodi di estensione definiti all'interno di dati tipi nella spazio dei nomi corrente o uno qualsiasi dei relativi elementi padre, gli spazi dei nomi figlio con precedenza maggiore rispetto a spazi dei nomi padre.  
  
3.  Metodi di estensione definiti in qualsiasi importazione di tipo nel file corrente.  
  
4.  Metodi di estensione definiti in qualsiasi importazione dello spazio dei nomi nel file corrente.  
  
5.  Metodi di estensione definiti in qualsiasi importazione di tipi a livello di progetto.  
  
6.  Metodi di estensione definiti in qualsiasi importazione dello spazio dei nomi a livello di progetto.  
  
 Se la precedenza non risolve l'ambiguità, è possibile usare il nome completo per specificare il metodo che si sta chiamando. Se il `Print` metodo nell'esempio precedente viene definito in un modulo denominato `StringExtensions`, specificare il nome completo viene `StringExtensions.Print(example)` invece di `example.Print()`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Metodi di estensione](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Istruzione Module](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Panoramica degli attributi](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
