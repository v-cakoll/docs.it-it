---
title: Funzionalità che supportano LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: 57c0566f9a76715e48b20f2e6493aa1a506c64be
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636861"
---
# <a name="visual-basic-features-that-support-linq"></a>Funzionalità di Visual Basic che supportano LINQ
Il nome Language-Integrated Query (LINQ) si riferisce alla tecnologia in Visual Basic che supporta la sintassi di query e altri costrutti di linguaggio direttamente nel linguaggio. Con LINQ non è necessario imparare un nuovo linguaggio per eseguire query su un'origine dati esterna. È possibile eseguire query sui dati in database relazionali, archivi XML o oggetti usando Visual Basic. Questa integrazione delle funzionalità di query nel linguaggio consente il controllo in fase di compilazione di errori di sintassi e indipendenza dai tipi. Questa integrazione garantisce anche la maggior parte delle informazioni necessarie per la scrittura di query complete e diversificate in Visual Basic.  
  
 Nelle sezioni seguenti vengono descritti i costrutti di linguaggio che supportano LINQ in modo sufficientemente dettagliato per poter iniziare a leggere la documentazione introduttiva, gli esempi di codice e le applicazioni di esempio. È anche possibile fare clic sui collegamenti per trovare una spiegazione più dettagliata del modo in cui le funzionalità del linguaggio sono disponibili per abilitare le query basate sulla lingua. Un punto di partenza ideale è la [procedura dettagliata: scrittura di query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Espressioni di query  
 Le espressioni di query in Visual Basic possono essere espresse in una sintassi dichiarativa simile a quella di SQL o XQuery. In fase di compilazione, la sintassi di query viene convertita in chiamate al metodo nell'implementazione di un provider LINQ dei metodi di estensione degli operatori di query standard. Le applicazioni controllano gli operatori di query standard inclusi nell'ambito specificando lo spazio dei nomi appropriato con un'istruzione `Imports`. La sintassi di un'espressione di query Visual Basic è simile alla seguente:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Per ulteriori informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variabili tipizzate in modo implicito  
 Anziché specificare in modo esplicito un tipo quando si dichiara e Inizializza una variabile, è possibile consentire al compilatore di dedurre e assegnare il tipo. Questa operazione viene definita *inferenza del tipo locale*.  
  
 Le variabili i cui tipi sono dedotti sono fortemente tipizzate, esattamente come le variabili il cui tipo è specificato in modo esplicito. L'inferenza del tipo locale funziona solo quando si definisce una variabile locale all'interno del corpo di un metodo. Per altre informazioni, vedere [istruzione Option deduce](../../../../visual-basic/language-reference/statements/option-infer-statement.md) e [inferenza del tipo locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Nell'esempio seguente viene illustrata l'inferenza del tipo locale. Per usare questo esempio, è necessario impostare `Option Infer` su `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 L'inferenza del tipo locale consente inoltre di creare tipi anonimi, descritti più avanti in questa sezione e sono necessari per le query LINQ.  
  
 Nell'esempio LINQ seguente, l'inferenza del tipo si verifica se `Option Infer` è `On` o `Off`. Si verifica un errore in fase di compilazione se `Option Infer` è `Off` e `Option Strict` è `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Inizializzatori di oggetti  
 Gli inizializzatori di oggetto vengono utilizzati nelle espressioni di query quando è necessario creare un tipo anonimo per contenere i risultati di una query. Possono inoltre essere utilizzati per inizializzare oggetti di tipi denominati all'esterno delle query. Utilizzando un inizializzatore di oggetto, è possibile inizializzare un oggetto in una singola riga senza chiamare esplicitamente un costruttore. Supponendo di avere una classe denominata `Customer` con proprietà `Name` e `Phone` pubbliche, insieme ad altre proprietà, è possibile usare un inizializzatore di oggetto in questo modo:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Per altre informazioni, vedere [inizializzatori di oggetto: tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipi anonimi  
 I tipi anonimi offrono un modo pratico per raggruppare temporaneamente un set di proprietà in un elemento che si desidera includere nel risultato di una query. In questo modo è possibile scegliere qualsiasi combinazione di campi disponibili nella query, in qualsiasi ordine, senza definire un tipo di dati denominato per l'elemento.  
  
 Un *tipo anonimo* viene costruito dinamicamente dal compilatore. Il nome del tipo viene assegnato dal compilatore e può essere modificato con ogni nuova compilazione. Il nome non può pertanto essere utilizzato direttamente. I tipi anonimi vengono inizializzati nel modo seguente:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Metodi di estensione  
 I metodi di estensione consentono di aggiungere metodi a un tipo di dati o a un'interfaccia dall'esterno della definizione. Questa funzionalità consente di aggiungere nuovi metodi a un tipo esistente senza modificare effettivamente il tipo. Gli operatori di query standard sono a loro volta un set di metodi di estensione che forniscono funzionalità di query LINQ per qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>. Altre estensioni da <xref:System.Collections.Generic.IEnumerable%601> includono <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>e <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Il metodo di estensione seguente aggiunge un metodo Print alla classe <xref:System.String>.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Il metodo viene chiamato come un metodo di istanza comune di <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Per altre informazioni, vedere [Metodi di estensione](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Espressioni lambda  
 Un'espressione lambda è una funzione senza nome che calcola e restituisce un singolo valore. Diversamente dalle funzioni denominate, un'espressione lambda può essere definita ed eseguita nello stesso momento. Nell'esempio seguente viene visualizzato 4.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 È possibile assegnare la definizione dell'espressione lambda a un nome di variabile e quindi usare il nome per chiamare la funzione. Nell'esempio seguente viene inoltre visualizzato 4.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 In LINQ, le espressioni lambda sono sottostanti molti degli operatori di query standard. Il compilatore crea espressioni lambda per acquisire i calcoli definiti nei metodi di query fondamentali, ad esempio `Where`, `Select`, `Order By`, `Take While`e altri.  
  
 Ad esempio, il codice seguente definisce una query che restituisce tutti gli studenti senior da un elenco di studenti.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 La definizione della query viene compilata nel codice che è simile all'esempio seguente, che usa due espressioni lambda per specificare gli argomenti per `Where` e `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 È possibile eseguire entrambe le versioni usando un ciclo `For Each`:  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Per altre informazioni, vedere [Espressioni lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [LINQ e stringhe (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
