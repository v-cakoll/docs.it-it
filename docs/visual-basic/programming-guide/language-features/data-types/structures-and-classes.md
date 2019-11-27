---
title: Strutture e classi
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 3353935a74bb77fa4a630e706aa425063c7a610a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346322"
---
# <a name="structures-and-classes-visual-basic"></a>Strutture e classi (Visual Basic)
Visual Basic unifica la sintassi per strutture e classi, con il risultato che entrambe le entità supportano la maggior parte delle stesse funzionalità. Tuttavia, esistono anche differenze importanti tra le strutture e le classi.  
  
 Le classi hanno il vantaggio di essere tipi di riferimento. il passaggio di un riferimento è più efficiente rispetto al passaggio di una variabile di struttura con tutti i relativi dati. D'altra parte, le strutture non richiedono l'allocazione della memoria nell'heap globale.  
  
 Poiché non è possibile ereditare da una struttura, le strutture devono essere usate solo per gli oggetti che non devono essere estesi. Usare le strutture quando l'oggetto che si vuole creare ha una dimensione di istanza ridotta e prendere in considerazione le caratteristiche di prestazioni delle classi rispetto alle strutture.  
  
## <a name="similarities"></a>Somiglianze  
 Le strutture e le classi sono simili nei seguenti aspetti:  
  
- Entrambi sono tipi di *contenitori* , ovvero contengono altri tipi come membri.  
  
- Entrambi hanno membri, che possono includere costruttori, metodi, proprietà, campi, costanti, enumerazioni, eventi e gestori eventi. Tuttavia, non confondere questi membri con gli *elementi* dichiarati di una struttura.  
  
- I membri di entrambi possono avere livelli di accesso personalizzati. Ad esempio, un membro può essere dichiarato `Public` e un altro `Private`.  
  
- Entrambi possono implementare interfacce.  
  
- Entrambi possono avere costruttori condivisi, con o senza parametri.  
  
- Entrambi possono esporre una *proprietà predefinita*, purché la proprietà accetti almeno un parametro.  
  
- Entrambi possono dichiarare e generare eventi ed entrambi possono dichiarare delegati.  
  
## <a name="differences"></a>Differenze  
 Le strutture e le classi differiscono dai seguenti elementi:  
  
- Le strutture sono *tipi valore*; le classi sono *tipi di riferimento*. Una variabile di un tipo di struttura contiene i dati della struttura, anziché contenere un riferimento ai dati come tipo di classe.  
  
- Le strutture usano l'allocazione dello stack; le classi usano l'allocazione heap.  
  
- Tutti gli elementi della struttura sono `Public` per impostazione predefinita. le variabili e le costanti della classe sono `Private` per impostazione predefinita, mentre altri membri della classe sono `Public` per impostazione predefinita. Questo comportamento per i membri della classe garantisce la compatibilità con il sistema Visual Basic 6,0 di impostazioni predefinite.  
  
- Una struttura deve avere almeno una variabile non condivisa o un elemento evento non condiviso, non personalizzato; una classe può essere completamente vuota.  
  
- Gli elementi della struttura non possono essere dichiarati come `Protected`; i membri della classe possono.  
  
- Una procedura di struttura può gestire gli eventi solo se si tratta di una procedura di`Sub` [condivisa](../../../../visual-basic/language-reference/modifiers/shared.md) e solo tramite l' [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md); qualsiasi routine di classe è in grado di gestire gli eventi tramite la parola chiave [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) o l'istruzione `AddHandler`. Per ulteriori informazioni, vedi [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
- Le dichiarazioni di variabili di struttura non possono specificare inizializzatori o dimensioni iniziali per le matrici; le dichiarazioni di variabili di classe possono.  
  
- Le strutture ereditano in modo implicito dalla classe <xref:System.ValueType?displayProperty=nameWithType> e non possono ereditare da altri tipi; le classi possono ereditare da una classe o da classi diverse da <xref:System.ValueType?displayProperty=nameWithType>.  
  
- Le strutture non sono ereditabili; le classi sono.  
  
- Le strutture non vengono mai terminate, quindi il Common Language Runtime (CLR) non chiama mai il metodo <xref:System.Object.Finalize%2A> su una struttura; le classi vengono terminate dal Garbage Collector (GC), che chiama <xref:System.Object.Finalize%2A> su una classe quando rileva che non sono presenti riferimenti attivi rimanenti.  
  
- Una struttura non richiede un costruttore. una classe.  
  
- Le strutture possono avere costruttori non condivisi solo se accettano parametri. le classi possono avere con o senza parametri.  
  
 Ogni struttura ha un costruttore pubblico implicito senza parametri. Questo costruttore inizializza tutti gli elementi dati della struttura sui valori predefiniti. Non è possibile ridefinire questo comportamento.  
  
## <a name="instances-and-variables"></a>Istanze e variabili  
 Poiché le strutture sono tipi di valore, ogni variabile di struttura viene associata in modo permanente a una singola istanza della struttura. Tuttavia, le classi sono tipi di riferimento e una variabile oggetto può fare riferimento a diverse istanze di classe in momenti diversi. Questa distinzione influiscono sull'utilizzo di strutture e classi nei modi seguenti:  
  
- **Inizializzazione.** Una variabile di struttura include implicitamente un'inizializzazione degli elementi usando il costruttore senza parametri della struttura. Pertanto, `Dim s As struct1` equivale a `Dim s As struct1 = New struct1()`.  
  
- **Assegnazione di variabili.** Quando si assegna una variabile di struttura a un'altra o si passa un'istanza della struttura a un argomento di routine, i valori correnti di tutti gli elementi variabili vengono copiati nella nuova struttura. Quando si assegna una variabile oggetto a un'altra o si passa una variabile oggetto a una routine, viene copiato solo il puntatore di riferimento.  
  
- **Assegnazione di Nothing.** È possibile assegnare il valore [Nothing](../../../../visual-basic/language-reference/nothing.md) a una variabile di struttura, ma l'istanza continua a essere associata alla variabile. È comunque possibile chiamare i relativi metodi e accedere ai relativi elementi dati, anche se gli elementi variabili vengono reinizializzati dall'assegnazione.  
  
     Al contrario, se si imposta una variabile oggetto su `Nothing`, l'associazione viene annullata da qualsiasi istanza di classe e non è possibile accedere ai membri tramite la variabile finché non viene assegnata un'altra istanza.  
  
- **Più istanze.** A una variabile oggetto possono essere assegnate istanze di classe diverse in momenti diversi e diverse variabili oggetto possono fare riferimento alla stessa istanza della classe nello stesso momento. Le modifiche apportate ai valori dei membri della classe hanno effetto su tali membri quando si accede tramite un'altra variabile che punta alla stessa istanza.  
  
     Gli elementi della struttura, tuttavia, sono isolati all'interno della propria istanza. Le modifiche ai valori non vengono riflesse in altre variabili di struttura, neanche in altre istanze della stessa dichiarazione di `Structure`.  
  
- **Uguaglianza.** I test di uguaglianza di due strutture devono essere eseguiti con un test elemento per elemento. È possibile confrontare due variabili oggetto utilizzando il metodo <xref:System.Object.Equals%2A>. <xref:System.Object.Equals%2A> indica se le due variabili puntano alla stessa istanza.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
