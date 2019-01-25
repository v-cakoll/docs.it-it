---
title: Strutture e classi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 78c1d529053a10fc208ee5499b759623c227cb25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681810"
---
# <a name="structures-and-classes-visual-basic"></a>Strutture e classi (Visual Basic)
Visual Basic unifica la sintassi per le strutture e classi, in modo che entrambe le entità supportano la maggior parte delle stesse funzionalità. Tuttavia, esistono anche differenze importanti tra classi e strutture.  
  
 Le classi hanno il vantaggio di essere tipi di riferimento, ovvero un riferimento a è più efficiente rispetto al passaggio di una variabile di struttura con tutti i relativi dati. D'altra parte, le strutture non richiedono l'allocazione di memoria nell'heap globale.  
  
 Poiché non è possibile ereditare da una struttura, strutture di usare solo per gli oggetti che non sono necessario essere esteso. Usare strutture quando l'oggetto a cui si vuole creare una dimensione di istanza piccola e prendere in considerazione le caratteristiche delle classi e strutture di prestazioni.  
  
## <a name="similarities"></a>Analogie  
 Classi e strutture sono simili per i seguenti aspetti:  
  
-   Sono entrambi *contenitore* tipi, vale a dire che devono contenere altri tipi di membri.  
  
-   Entrambi hanno membri, che possono includere costruttori, metodi, proprietà, campi, le costanti, enumerazioni, eventi e gestori di eventi. Tuttavia, non confondere questi membri con dichiarato *elementi* di una struttura.  
  
-   I membri di entrambi possono avere livelli di accesso personalizzati. Ad esempio, un membro può essere dichiarato `Public` e un altro `Private`.  
  
-   Entrambi possono implementare interfacce.  
  
-   Entrambi possono avere condivisi costruttori, con o senza parametri.  
  
-   Entrambi possono esporre una *predefiniti delle proprietà*, purché tali proprietà richiede almeno un parametro.  
  
-   Sia possibile dichiarare e generare eventi e sia possibile dichiarare i delegati.  
  
## <a name="differences"></a>Differenze  
 Classi e strutture sono diversi per le indicazioni seguenti:  
  
-   Le strutture sono *i tipi di valore*; le classi sono *fanno riferimento ai tipi*. Una variabile di un tipo di struttura contiene i dati della struttura, anziché che contiene un riferimento ai dati come un tipo di classe.  
  
-   Strutture di utilizzano l'allocazione dello stack; classi usano allocazione dell'heap.  
  
-   Tutti gli elementi di struttura sono `Public` per impostazione predefinita; classe variabili e costanti rappresentano `Private` per impostazione predefinita, mentre altri membri della classe sono `Public` per impostazione predefinita. Questo comportamento per i membri di classi fornisce la compatibilità con il sistema di Visual Basic 6.0 di valori predefiniti.  
  
-   Una struttura deve avere almeno un non personalizzato non condiviso di variabile o condiviso, elemento di un evento; una classe può essere completamente vuota.  
  
-   Gli elementi di struttura non possono essere dichiarati come `Protected`; i membri di classe possono.  
  
-   Una routine di struttura può gestire gli eventi solo se è un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` routine e solo per mezzo del [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md); qualsiasi routine della classe può gestire gli eventi utilizzando entrambi il [ Gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) parola chiave o il `AddHandler` istruzione. Per altre informazioni, vedere [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Le dichiarazioni di variabili di struttura non possono specificare inizializzatori o dimensioni iniziali per le matrici. le dichiarazioni di variabili di classe possono.  
  
-   Le strutture ereditano in modo implicito dal <xref:System.ValueType?displayProperty=nameWithType> classe e non può ereditare da qualsiasi altro tipo; le classi possono ereditare da qualsiasi classe o classi diverso da <xref:System.ValueType?displayProperty=nameWithType>.  
  
-   Strutture non sono ereditabili; le classi sono.  
  
-   Le strutture non sono mai terminate, common language runtime (CLR) non chiama mai il <xref:System.Object.Finalize%2A> metodo su qualsiasi struttura; le classi vengono terminate dal garbage collector (GC), che chiama <xref:System.Object.Finalize%2A> in una classe quando rileva non sono presenti riferimenti attivi rimanenti.  
  
-   Una struttura non richiede un costruttore. esegue una classe.  
  
-   Le strutture possono contenere costruttori non condivisi solo se si accettano parametri; le classi possibile configurarli con o senza parametri.  
  
 Ogni struttura dispone di un costruttore pubblico senza parametri. Questo costruttore inizializza gli elementi di dati della struttura per i relativi valori predefiniti. Non è possibile ridefinire il problema.  
  
## <a name="instances-and-variables"></a>Istanze e variabili  
 Poiché le strutture sono tipi valore, ogni variabile di struttura in modo permanente è associato a un'istanza di singole strutture. Ma le classi sono tipi riferimento e una variabile oggetto può fare riferimento a diverse istanze di classi in momenti diversi. Questa differenza influisce sull'utilizzo di strutture e classi nei modi seguenti:  
  
-   **Inizializzazione.** Una variabile di struttura in modo implicito include un'inizializzazione degli elementi usando il costruttore della struttura senza parametri. Pertanto `Dim s As struct1` equivale a `Dim s As struct1 = New struct1()`.  
  
-   **Assegnazione di variabili.** Quando si assegna una variabile di struttura a un altro, o passa un'istanza della struttura a un argomento di routine, vengono copiati i valori correnti di tutti gli elementi variabili con la nuova struttura. Quando si assegna una variabile oggetto in un altro o passarla una variabile oggetto a una routine, viene copiato solo il puntatore di riferimento.  
  
-   **Assegnare il valore Nothing.** È possibile assegnare il valore [Nothing](../../../../visual-basic/language-reference/nothing.md) a una struttura di variabile, ma l'istanza continua a essere associato alla variabile. È comunque possibile chiamarne i metodi e accedere ai relativi elementi di dati, anche se gli elementi variabili vengono reinizializzati dall'assegnazione.  
  
     Al contrario, se si imposta una variabile oggetto `Nothing`annullarne l'associazione da qualsiasi istanza della classe e non può accedere ad alcun membro attraverso la variabile di fino a quando non si assegna un'altra istanza ad esso.  
  
-   **Più istanze.** Una variabile oggetto può avere istanze della classe diversi assegnate in momenti diversi e diverse variabili oggetto facciano riferimento alla stessa istanza di classe nello stesso momento. Le modifiche apportate ai valori dei membri della classe influiscono su quei membri quando si accede tramite un'altra variabile che puntano alla stessa istanza.  
  
     Elementi della struttura, tuttavia, sono isolati all'interno della relativa istanza. I valori non vengono riflesse nelle altre variabili di struttura, anche in altre istanze dello stesso `Structure` dichiarazione.  
  
-   **Equality.** Il test di uguaglianza di due strutture deve essere eseguito con un elemento per elemento test. Due variabili oggetto possono essere confrontate utilizzando il <xref:System.Object.Equals%2A> (metodo). <xref:System.Object.Equals%2A> indica se le due variabili puntano alla stessa istanza.  
  
## <a name="see-also"></a>Vedere anche
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
