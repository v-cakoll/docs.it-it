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
ms.openlocfilehash: d252d9216a9b825ad0663a5779d7ce7f81fa9011
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393572"
---
# <a name="structures-and-classes-visual-basic"></a>Strutture e classi (Visual Basic)
Visual Basic unifica la sintassi per strutture e classi, con il risultato che entrambe le entità supportano la maggior parte delle stesse funzionalità. Tuttavia, esistono anche differenze importanti tra le strutture e le classi.  
  
 Le classi hanno il vantaggio di essere tipi di riferimento. il passaggio di un riferimento è più efficiente rispetto al passaggio di una variabile di struttura con tutti i relativi dati. D'altra parte, le strutture non richiedono l'allocazione della memoria nell'heap globale.  
  
 Poiché non è possibile ereditare da una struttura, le strutture devono essere usate solo per gli oggetti che non devono essere estesi. Usare le strutture quando l'oggetto che si vuole creare ha una dimensione di istanza ridotta e prendere in considerazione le caratteristiche di prestazioni delle classi rispetto alle strutture.  
  
## <a name="similarities"></a>Somiglianze  
 Le strutture e le classi sono simili nei seguenti aspetti:  
  
- Entrambi sono tipi di *contenitori* , ovvero contengono altri tipi come membri.  
  
- Entrambi hanno membri, che possono includere costruttori, metodi, proprietà, campi, costanti, enumerazioni, eventi e gestori eventi. Tuttavia, non confondere questi membri con gli *elementi* dichiarati di una struttura.  
  
- I membri di entrambi possono avere livelli di accesso personalizzati. Ad esempio, un membro può essere dichiarato `Public` e un altro `Private` .  
  
- Entrambi possono implementare interfacce.  
  
- Entrambi possono avere costruttori condivisi, con o senza parametri.  
  
- Entrambi possono esporre una *proprietà predefinita*, purché la proprietà accetti almeno un parametro.  
  
- Entrambi possono dichiarare e generare eventi ed entrambi possono dichiarare delegati.  
  
## <a name="differences"></a>Differenze  
 Le strutture e le classi differiscono dai seguenti elementi:  
  
- Le strutture sono *tipi valore*; le classi sono *tipi di riferimento*. Una variabile di un tipo di struttura contiene i dati della struttura, anziché contenere un riferimento ai dati come tipo di classe.  
  
- Le strutture usano l'allocazione dello stack; le classi usano l'allocazione heap.  
  
- Tutti gli elementi della struttura sono `Public` per impostazione predefinita. le variabili di classe e le costanti sono per impostazione predefinita `Private` , mentre altri membri della classe sono `Public` per impostazione predefinita. Questo comportamento per i membri della classe garantisce la compatibilità con il sistema Visual Basic 6,0 di impostazioni predefinite.  
  
- Una struttura deve avere almeno una variabile non condivisa o un elemento evento non condiviso, non personalizzato; una classe può essere completamente vuota.  
  
- Gli elementi della struttura non possono essere dichiarati come `Protected` . i membri della classe possono.  
  
- Una procedura di struttura è in grado di gestire gli eventi solo se si tratta di una procedura [condivisa](../../../language-reference/modifiers/shared.md) `Sub` e solo tramite l' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md); qualsiasi routine della classe può gestire gli eventi, utilizzando la parola chiave [Handles](../../../language-reference/statements/handles-clause.md) o l' `AddHandler` istruzione. Per altre informazioni, vedere [Eventi](../events/index.md).  
  
- Le dichiarazioni di variabili di struttura non possono specificare inizializzatori o dimensioni iniziali per le matrici; le dichiarazioni di variabili di classe possono.  
  
- Le strutture ereditano in modo implicito dalla <xref:System.ValueType?displayProperty=nameWithType> classe e non possono ereditare da altri tipi. le classi possono ereditare da qualsiasi classe o classe diversa da <xref:System.ValueType?displayProperty=nameWithType> .  
  
- Le strutture non sono ereditabili; le classi sono.  
  
- Le strutture non vengono mai terminate, quindi il Common Language Runtime (CLR) non chiama mai il <xref:System.Object.Finalize%2A> metodo su una struttura; le classi vengono terminate dalla Garbage Collector (GC), che chiama <xref:System.Object.Finalize%2A> su una classe quando rileva che non sono presenti riferimenti attivi rimanenti.  
  
- Una struttura non richiede un costruttore. una classe.  
  
- Le strutture possono avere costruttori non condivisi solo se accettano parametri. le classi possono avere con o senza parametri.  
  
 Ogni struttura ha un costruttore pubblico implicito senza parametri. Questo costruttore inizializza tutti gli elementi dati della struttura sui valori predefiniti. Non è possibile ridefinire questo comportamento.  
  
## <a name="instances-and-variables"></a>Istanze e variabili  
 Poiché le strutture sono tipi di valore, ogni variabile di struttura viene associata in modo permanente a una singola istanza della struttura. Tuttavia, le classi sono tipi di riferimento e una variabile oggetto può fare riferimento a diverse istanze di classe in momenti diversi. Questa distinzione influiscono sull'utilizzo di strutture e classi nei modi seguenti:  
  
- **Inizializzazione.** Una variabile di struttura include implicitamente un'inizializzazione degli elementi usando il costruttore senza parametri della struttura. Pertanto, `Dim s As struct1` equivale a `Dim s As struct1 = New struct1()` .  
  
- **Assegnazione di variabili.** Quando si assegna una variabile di struttura a un'altra o si passa un'istanza della struttura a un argomento di routine, i valori correnti di tutti gli elementi variabili vengono copiati nella nuova struttura. Quando si assegna una variabile oggetto a un'altra o si passa una variabile oggetto a una routine, viene copiato solo il puntatore di riferimento.  
  
- **Assegnazione di Nothing.** È possibile assegnare il valore [Nothing](../../../language-reference/nothing.md) a una variabile di struttura, ma l'istanza continua a essere associata alla variabile. È comunque possibile chiamare i relativi metodi e accedere ai relativi elementi dati, anche se gli elementi variabili vengono reinizializzati dall'assegnazione.  
  
     Al contrario, se si imposta una variabile oggetto su, l'associazione viene `Nothing` annullata da qualsiasi istanza di classe e non è possibile accedere ai membri tramite la variabile finché non viene assegnata un'altra istanza.  
  
- **Più istanze.** A una variabile oggetto possono essere assegnate istanze di classe diverse in momenti diversi e diverse variabili oggetto possono fare riferimento alla stessa istanza della classe nello stesso momento. Le modifiche apportate ai valori dei membri della classe hanno effetto su tali membri quando si accede tramite un'altra variabile che punta alla stessa istanza.  
  
     Gli elementi della struttura, tuttavia, sono isolati all'interno della propria istanza. Le modifiche apportate ai valori non vengono riflesse in altre variabili di struttura, neanche in altre istanze della stessa `Structure` dichiarazione.  
  
- **Uguaglianza.** I test di uguaglianza di due strutture devono essere eseguiti con un test elemento per elemento. È possibile confrontare due variabili oggetto utilizzando il <xref:System.Object.Equals%2A> metodo. <xref:System.Object.Equals%2A>indica se le due variabili puntano alla stessa istanza.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Tipi di dati compositi](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Strutture](structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Strutture e altri elementi di programmazione](structures-and-other-programming-elements.md)
- [Oggetti e classi](../objects-and-classes/index.md)
