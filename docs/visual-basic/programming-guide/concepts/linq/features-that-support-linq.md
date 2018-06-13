---
title: Funzionalità di Visual Basic che supportano LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: db2eff2f7c19a3c510e7b212f5bb406d7a885439
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643900"
---
# <a name="visual-basic-features-that-support-linq"></a>Funzionalità di Visual Basic che supportano LINQ
Il nome [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] si riferisce alla tecnologia in Visual Basic che supporta la sintassi della query e altri costrutti linguaggio direttamente nel linguaggio. Con [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], non è necessario imparare un nuovo linguaggio di query su un'origine dati esterna. È possibile eseguire query sui dati in database relazionali, archivi XML o gli oggetti utilizzando Visual Basic. Questa integrazione delle funzionalità di query nel linguaggio consente di controllo in fase di compilazione per gli errori di sintassi e indipendenza dai tipi. Questa integrazione garantisce inoltre che si conosce già la maggior parte delle informazioni necessarie per poter scrivere query complesse in Visual Basic.  
  
 Nelle sezioni seguenti vengono descritti i costrutti di linguaggio che supportano LINQ informazioni sufficienti per consentire di iniziare a leggere la documentazione introduttiva, esempi di codice e applicazioni di esempio. È anche possibile fare clic sui collegamenti per informazioni più dettagliate di come le funzionalità del linguaggio per la convergenza abilitare language integrated query. È un buon punto di partenza [procedura dettagliata: scrittura di query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Espressioni di query  
 Espressioni di query in Visual Basic possono essere espresso in una sintassi dichiarativa simile a quella di SQL o XQuery. In fase di compilazione, la sintassi di query viene convertita in chiamate al metodo di implementazione di un provider LINQ dei metodi di estensione operatore query standard. Controllo delle applicazioni presenti nell'ambito di operatori di query standard, specificando lo spazio dei nomi appropriato con un `Imports` istruzione. Sintassi per un'espressione di query di Visual Basic è simile al seguente:  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Per ulteriori informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Variabili tipizzate in modo implicito  
 Anziché specificare in modo esplicito un tipo quando è necessario dichiarare e inizializzare una variabile, è possibile abilitare il compilatore di dedurre e assegnare il tipo. Ciò è detto *inferenza*.  
  
 Le variabili i cui tipi inferiti sono fortemente tipizzate, proprio come le variabili il cui tipo è specificare in modo esplicito. L'inferenza del tipo locale funziona solo quando si definisce una variabile locale all'interno di un corpo del metodo. Per ulteriori informazioni, vedere [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) e [locale l'inferenza del tipo](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 L'esempio seguente illustra l'inferenza del tipo locale. Per usare questo esempio, è necessario impostare `Option Infer` a `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Inferenza dei tipi locali rende inoltre possibile creare tipi anonimi, che vengono descritti più avanti in questa sezione e sono necessari per le query LINQ.  
  
 Nell'esempio seguente LINQ, si verifica l'inferenza del tipo se `Option Infer` è `On` o `Off`. Si verifica un errore in fase di compilazione se `Option Infer` è `Off` e `Option Strict` è `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Inizializzatori di oggetti  
 Gli inizializzatori di oggetto utilizzati nelle espressioni di query quando è necessario creare un tipo anonimo per archiviare i risultati di una query. Inoltre possono essere utilizzati per inizializzare oggetti di tipi denominati all'esterno delle query. Utilizzando un inizializzatore di oggetto, è possibile inizializzare un oggetto in una singola riga senza chiamare in modo esplicito un costruttore. Supponendo che sia presente una classe denominata `Customer` con pubblica `Name` e `Phone` proprietà, insieme ad altre proprietà, un inizializzatore di oggetto può essere utilizzato in questo modo:  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Per ulteriori informazioni, vedere [gli inizializzatori di oggetto: tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Tipi anonimi  
 Tipi anonimi consentono di raggruppare temporaneamente un set di proprietà in un elemento che si desidera includere nel risultato di una query. In questo modo è possibile scegliere qualsiasi combinazione di campi disponibili nella query, in qualsiasi ordine, senza definire un tipo di dati denominato per l'elemento.  
  
 Un *tipo anonimo* viene costruito dinamicamente dal compilatore. Il nome del tipo è assegnato dal compilatore e può cambiare a ogni nuova compilazione. Pertanto, il nome non può essere utilizzato direttamente. Tipi anonimi vengono inizializzati nel modo seguente:  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Metodi di estensione  
 Metodi di estensione consentono di aggiungere metodi a un tipo di dati o un'interfaccia all'esterno la definizione. Questa funzionalità consente di aggiungere in effetti, i nuovi metodi a un tipo esistente senza modificare il tipo. Gli operatori query standard sono a loro volta una serie di metodi di estensione che forniscono [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] funzionalità di query per qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>. Altre estensioni a <xref:System.Collections.Generic.IEnumerable%601> includono <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, e <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Il metodo di estensione seguente aggiunge un metodo di stampa per la <xref:System.String> classe.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Viene chiamato il metodo come metodo di istanza comune di <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Per altre informazioni, vedere [Metodi di estensione](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Espressioni lambda  
 Un'espressione lambda è una funzione senza nome, che calcola e restituisce un valore singolo. A differenza delle funzioni denominate, un'espressione lambda può essere definita ed eseguita nello stesso momento. Nell'esempio seguente viene visualizzato 4.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 È possibile assegnare la definizione dell'espressione lambda a un nome di variabile e quindi usare il nome per chiamare la funzione. Nell'esempio seguente viene visualizzato anche 4.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], espressioni lambda sottostanti molti degli operatori di query standard. Il compilatore crea le espressioni lambda per acquisire i calcoli definiti nei metodi di query fondamentali, ad esempio `Where`, `Select`, `Order By`, `Take While`e altri.  
  
 Ad esempio, il codice seguente definisce una query che restituisce tutti gli studenti senior da un elenco di studenti.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 La definizione della query viene compilata nel codice che è simile all'esempio seguente, che utilizza due espressioni lambda per specificare gli argomenti per `Where` e `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 È possibile eseguire entrambe le versioni con un `For Each` ciclo:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Per altre informazioni, vedere [Espressioni lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [LINQ e stringhe (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
