---
title: Funzionalità di Visual Basic che supportano LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: 155d5c36483accc12d066a5530fea20a563e1498
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977561"
---
# <a name="visual-basic-features-that-support-linq"></a>Funzionalità di Visual Basic che supportano LINQ
Il nome [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] si riferisce alla tecnologia in Visual Basic che supporta la sintassi della query e altri linguaggio costruisce direttamente nel linguaggio. Con [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], non devi imparare un nuovo linguaggio di query su un'origine dati esterna. È possibile eseguire query sui dati archiviati in database relazionali, archivi XML o oggetti mediante Visual Basic. Questa integrazione delle funzionalità di query nel linguaggio consente in fase di compilazione cercano gli errori di sintassi e indipendenza dai tipi. Questa integrazione assicura anche che si conosce già la maggior parte di ciò che devi sapere per scrivere query complesse in Visual Basic.  
  
 Le sezioni seguenti descrivono i costrutti di linguaggio che supportano LINQ in maniera più approfondita che consentono di iniziare a leggere la documentazione introduttiva, esempi di codice e applicazioni di esempio. È anche possibile fare clic sui collegamenti per trovare una spiegazione più dettagliata del modo in cui le funzionalità del linguaggio si riuniscono per abilitare le query Linq. È un buon punto di partenza [procedura dettagliata: Scrittura di query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Espressioni di query  
 Espressioni di query in Visual Basic possono essere espresso in una sintassi dichiarativa simile a quella di SQL o XQuery. In fase di compilazione, la sintassi di query viene convertita in chiamate al metodo di implementazione di un provider LINQ di ai metodi di estensione dell'operatore query standard. Le applicazioni controllano gli operatori query standard sono nell'ambito specificando lo spazio dei nomi appropriato con un `Imports` istruzione. Sintassi per un'espressione di query di Visual Basic è simile alla seguente:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Per altre informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variabili tipizzate in modo implicito  
 Anziché specificare in modo esplicito un tipo quando si dichiara e Inizializza una variabile, è possibile abilitare il compilatore di dedurre e assegnare il tipo. Ciò è detto *inferenza del tipo locale*.  
  
 Le variabili i cui tipi inferiti sono fortemente tipizzate, proprio come le variabili il cui tipo è specificare in modo esplicito. L'inferenza del tipo locale funziona solo quando si definisce una variabile locale all'interno di un corpo del metodo. Per altre informazioni, vedere [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) e [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 L'esempio seguente illustra l'inferenza del tipo locale. Per usare questo esempio, è necessario impostare `Option Infer` a `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 L'inferenza del tipo locale rende inoltre possibile creare i tipi anonimi, che sono descritte più avanti in questa sezione e sono necessari per le query LINQ.  
  
 Nell'esempio seguente di LINQ, si verifica l'inferenza del tipo se `Option Infer` può essere `On` o `Off`. Si verifica un errore in fase di compilazione se `Option Infer` viene `Off` e `Option Strict` è `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Inizializzatori di oggetti  
 Gli inizializzatori di oggetto utilizzati nelle espressioni di query quando è necessario creare un tipo anonimo per archiviare i risultati di una query. Possono essere usati anche per inizializzare oggetti di tipi denominati all'esterno delle query. Usando un inizializzatore di oggetto, è possibile inizializzare un oggetto in una singola riga senza chiamare in modo esplicito un costruttore. Supponendo che sia presente una classe denominata `Customer` dotato pubbliche `Name` e `Phone` proprietà, insieme ad altre proprietà, un inizializzatore di oggetto può essere usato in questo modo:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Per altre informazioni, vedere [gli inizializzatori di oggetto: Tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipi anonimi  
 I tipi anonimi offrono un modo pratico per raggruppare temporaneamente un set di proprietà in un elemento che si desidera includere nei risultati della query. In questo modo è possibile scegliere qualsiasi combinazione di campi disponibili nella query, in qualsiasi ordine, senza definire un tipo di dati con nome per l'elemento.  
  
 Un' *tipo anonimo* viene costruito in modo dinamico dal compilatore. Il nome del tipo è assegnato dal compilatore e può cambiare a ogni nuova compilazione. Pertanto, il nome non può essere utilizzato direttamente. I tipi anonimi vengono inizializzati nel modo seguente:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Metodi di estensione  
 I metodi di estensione consentono di aggiungere metodi a un tipo di dati o un'interfaccia all'esterno la definizione. Questa funzionalità consente in effetti, aggiungere nuovi metodi a un tipo esistente senza modificare il tipo. Gli operatori query standard fanno un set di metodi di estensione che forniscono [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] funzionalità di query per qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>. Altre estensioni <xref:System.Collections.Generic.IEnumerable%601> comprendono <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, e <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Il metodo di estensione seguente aggiunge un metodo di stampa per il <xref:System.String> classe.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Il metodo viene chiamato come metodo di istanza comune di <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Per altre informazioni, vedere [Metodi di estensione](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Espressioni lambda  
 Un'espressione lambda è una funzione senza nome, che calcola e restituisce un valore singolo. A differenza delle funzioni denominate, un'espressione lambda può essere definita ed eseguita nello stesso momento. Nell'esempio seguente vengono visualizzate 4.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 È possibile assegnare la definizione dell'espressione lambda a un nome di variabile e quindi usare il nome per chiamare la funzione. L'esempio seguente mostra anche 4.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], espressioni lambda sono alla base di molti degli operatori query standard. Il compilatore crea le espressioni lambda per acquisire i calcoli definiti, ad esempio nei metodi di query fondamentali `Where`, `Select`, `Order By`, `Take While`e così via.  
  
 Ad esempio, il codice seguente definisce una query che restituisce tutti gli studenti senior da un elenco di studenti.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 La definizione della query viene compilata nel codice che è simile all'esempio seguente, che usa due espressioni lambda per specificare gli argomenti per `Where` e `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 Entrambe le versioni possono essere eseguita tramite un `For Each` ciclo:  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Per altre informazioni, vedere [Espressioni lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [LINQ e stringhe (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
