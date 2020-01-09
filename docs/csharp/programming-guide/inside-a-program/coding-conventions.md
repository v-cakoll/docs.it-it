---
title: Convenzioni di codifica C# - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: c56d673de958f49a9ace60350442e89039e1d69f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712104"
---
# <a name="c-coding-conventions-c-programming-guide"></a>Convenzioni di codifica C# (Guida per programmatori C#)
 Le convenzioni di codifica hanno gli scopi seguenti:  
  
- Creano un aspetto coerente per il codice in modo che chi legge possa concentrarsi sul contenuto, non sul layout.  
  
- Consentono a chi legge di comprendere il codice più rapidamente, formulando presupposti basati sulle esperienze precedenti.  
  
- Facilitano la copia, la modifica e la gestione del codice.  
  
- Illustrano procedure consigliate di C#.  

 Le linee guida riportate in questo argomento vengono usate da Microsoft per sviluppare gli esempi e la documentazione.  
  
## <a name="naming-conventions"></a>Convenzioni di denominazione  
  
- Negli esempi brevi che non includono [direttive using](../../language-reference/keywords/using-directive.md), usare qualifiche dello spazio dei nomi. Se si è certi che uno spazio dei nomi viene importato per impostazione predefinita in un progetto, non è necessario specificare in modo completo i nomi da tale spazio dei nomi. I nomi completi possono essere interrotti dopo un punto (.) se sono troppo lunghi per una singola riga, come illustrato nell'esempio seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- Non è necessario modificare i nomi degli oggetti creati usando gli strumenti di progettazione di Visual Studio per adattarli ad altre linee guida.  
  
## <a name="layout-conventions"></a>Convenzioni di layout  
 Un layout appropriato usa la formattazione per mettere in evidenza la struttura del codice e per facilitare la lettura del codice. Gli esempi Microsoft sono conformi alle convenzioni seguenti:  
  
- Usare le impostazioni dell'Editor di codice predefinite (rientri intelligenti, rientri di quattro caratteri, tabulazioni salvate come spazi). Per altre informazioni, vedere [Opzioni, Editor di testo, C#, Formattazione](/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
- Scrivere una sola istruzione per riga.  
  
- Scrivere una sola dichiarazione per riga.  
  
- Se le righe di continuazione non sono rientrate automaticamente, impostare un rientro con un punto di tabulazione (quattro spazi).  
  
- Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.  
  
- Usare le parentesi per rendere visibili le clausole in un'espressione, come illustrato nel codice seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a>Convenzioni relative ai commenti  
  
- Posizionare il commento su una riga separata, non alla fine di una riga di codice.  
  
- Iniziare il commento con una lettera maiuscola.  
  
- Terminare il commento con un punto finale.  
  
- Inserire uno spazio tra i delimitatori di commento (//) e il testo del commento, come illustrato nell'esempio seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- Non creare blocchi formattati di asterischi intorno ai commenti.  
  
## <a name="language-guidelines"></a>Linee guida della lingua  
 Nelle sezioni seguenti vengono descritte le procedure che il team C# deve seguire per preparare campioni ed esempi di codice.  
  
### <a name="string-data-type"></a>Tipo di dati String  
  
- Usare l'[interpolazione di stringhe](../../language-reference/tokens/interpolated.md) per concatenare stringhe brevi, come illustrato nel codice seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- Per accodare stringhe nei cicli, specialmente quando si lavora con grandi quantità di testo, usare un oggetto <xref:System.Text.StringBuilder>.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a>Variabili locali tipizzate in modo implicito  
  
- Usare la [tipizzazione implicita](../classes-and-structs/implicitly-typed-local-variables.md) per le variabili locali quando il tipo della variabile è ovvio dal lato destro dell'assegnazione o il tipo preciso non è importante.  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- Non usare [var](../../language-reference/keywords/var.md) quando il tipo non è evidente dal lato destro dell'assegnazione.  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- Non basarsi sul nome della variabile per specificare il tipo della variabile. Potrebbe non essere corretto.  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- Evitare l'uso di `var` al posto di [dynamic](../../language-reference/builtin-types/reference-types.md).  
  
- Usare la tipizzazione implicita per determinare il tipo della variabile del ciclo nei cicli [for](../../language-reference/keywords/for.md) e [foreach](../../language-reference/keywords/foreach-in.md).  
  
     Nell'esempio seguente viene usata la tipizzazione implicita in un'istruzione `for`.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
     Nell'esempio seguente viene usata la tipizzazione implicita in un'istruzione `foreach`.  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a>Tipi di dati non firmati  
  
- In generale, usare `int` anziché tipi non firmati. L'utilizzo di `int` è comune in C# ed è più facile interagire con altre librerie, quando si usa `int`.  
  
### <a name="arrays"></a>Array  
  
- Usare la sintassi concisa quando si inizializzano le matrici nella riga della dichiarazione.  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a>Delegati  
  
- Usare la sintassi concisa per creare istanze di un tipo delegato.  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>Istruzioni try-catch e using nella gestione delle eccezioni  
  
- Usare un'istruzione [try-catch](../../language-reference/keywords/try-catch.md) per la gestione della maggior parte delle eccezioni.  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- Semplificare il codice usando l'[istruzione using](../../language-reference/keywords/using-statement.md) di C#. Se si ha un'istruzione [try-finally](../../language-reference/keywords/try-finally.md) in cui l'unico codice nel blocco `finally` è una chiamata al metodo <xref:System.IDisposable.Dispose%2A>, usare invece un'istruzione `using`.  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a>Operatori && e &#124;&#124;  
  
- Per evitare eccezioni e migliorare le prestazioni ignorando i confronti non necessari, usare [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) invece di [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) e [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) invece di [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) quando si eseguono confronti, come illustrato nell'esempio seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a>Operatore New  
  
- Usare il modulo conciso della creazione dell'istanza di oggetto, con la tipizzazione implicita, come illustrato nella dichiarazione seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     La riga precedente è equivalente alla dichiarazione seguente.  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- Usare gli inizializzatori di oggetto per semplificare la creazione di un oggetto.  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a>Gestione di eventi  
  
- Se si definisce un gestore eventi che non è necessario rimuovere successivamente, usare un'espressione lambda.  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a>Membri static  
  
- Chiamare i membri [static](../../language-reference/keywords/static.md) usando il nome della classe: *ClassName.StaticMember*. Questa pratica rende più leggibile il codice semplificando l'accesso statico.  Non qualificare un membro statico definito in una classe base con il nome di una classe derivata.  Nonostante il codice venga compilato, la leggibilità del codice è fuorviante mentre il codice potrebbe essere interrotto in futuro, se si aggiunge un membro statico con lo stesso nome alla classe derivata.  
  
### <a name="linq-queries"></a>Query LINQ  
  
- Usare nomi significativi per le variabili di query. Nell'esempio seguente viene usato `seattleCustomers` per i clienti che si trovano a Seattle.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Usare gli alias per assicurarsi che i nomi delle proprietà di tipi anonimi siano scritti correttamente in maiuscolo, usando la convenzione Pascal.  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui. Ad esempio, se la query restituisce un nome cliente un ID del server di distribuzione, anziché lasciarli come `Name` e `ID` nei risultati, rinominarli per spiegare che `Name` è il nome di un cliente e `ID` è l'ID di un server di distribuzione.  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- Usare la tipizzazione implicita nella dichiarazione di variabili di query e variabili di intervallo.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Allineare le clausole di query sotto la clausola [from](../../language-reference/keywords/from-clause.md), come illustrato negli esempi precedenti.  
  
- Usare le clausole [where](../../language-reference/keywords/where-clause.md) prima delle altre clausole di query, per garantire che le clausole di query successive agiscano su un set di dati ridotto e filtrato.  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- Usare più clausole `from` invece di una clausola [join](../../language-reference/keywords/join-clause.md) per accedere a raccolte interne. Ad esempio, ogni raccolta di oggetti `Student` potrebbe contenere una raccolta di punteggi del test. Quando viene eseguita la query seguente, viene restituito ogni punteggio superiore a 90, e il cognome dello studente che ha ricevuto il punteggio.  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a>Sicurezza -  
 Seguire le indicazioni in [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md).  
  
## <a name="see-also"></a>Vedere anche

- [Convenzioni di scrittura codice di Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md)
