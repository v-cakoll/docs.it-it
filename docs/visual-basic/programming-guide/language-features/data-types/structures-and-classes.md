---
title: Strutture e classi (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf72fb0a7a34d45774cb9a58c037ebcb1c05288f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="structures-and-classes-visual-basic"></a>Strutture e classi (Visual Basic)
Visual Basic unifica la sintassi per le strutture e classi, con il risultato che entrambe le entità supportano la maggior parte delle stesse funzionalità. Tuttavia, esistono anche differenze importanti tra le classi e strutture.  
  
 Classi hanno il vantaggio di essere tipi di riferimento, passando un riferimento è più efficiente del passaggio di una variabile di struttura con tutti i relativi dati. D'altra parte, le strutture non richiedono l'allocazione di memoria nell'heap globale.  
  
 Perché non è possibile ereditare da una struttura, le strutture devono essere utilizzate solo per gli oggetti che non è necessario estendere. Quando l'oggetto a cui si desidera creare una dimensione piccola istanza e prendere in considerazione le caratteristiche delle classi e strutture di prestazioni, utilizzare le strutture.  
  
## <a name="similarities"></a>Analogie  
 Classi e strutture sono simili per i seguenti aspetti:  
  
-   Entrambi sono *contenitore* tipi, vale a dire che contengono altri tipi come membri.  
  
-   Entrambi disporre di membri, che possono includere costruttori, metodi, proprietà, campi, costanti, enumerazioni, eventi e gestori eventi. Tuttavia, è importante non confondere questi membri con dichiarato *elementi* di una struttura.  
  
-   I membri di entrambi possono avere livelli di accesso personalizzati. Ad esempio, è possibile dichiarare un membro `Public` e un altro `Private`.  
  
-   Entrambi possono implementare interfacce.  
  
-   Entrambi possono avere condivisi costruttori, con o senza parametri.  
  
-   Entrambe possono esporre un *proprietà predefinita*, a condizione che accetti almeno un parametro.  
  
-   Entrambe possono dichiarare e generare eventi e sia possibile dichiarare i delegati.  
  
## <a name="differences"></a>Differenze  
 Strutture e classi si differenziano per i seguenti aspetti:  
  
-   Le strutture sono *i tipi di valore*; le classi sono *tipi di riferimento*. Una variabile di un tipo di struttura contiene i dati della struttura, anziché contenente un riferimento ai dati come un tipo di classe.  
  
-   Strutture di utilizzano l'allocazione dello stack; classi di utilizzano l'allocazione di heap.  
  
-   Tutti gli elementi di struttura sono `Public` per impostazione predefinita; classe variabili e costanti sono `Private` per impostazione predefinita, mentre altri membri della classe sono `Public` per impostazione predefinita. Questo comportamento per i membri di classe garantisce la compatibilità con il sistema di Visual Basic 6.0 di impostazioni predefinite.  
  
-   Una struttura deve avere almeno uno non personalizzato non condiviso di variabile o condiviso, elemento di un evento; una classe può essere completamente vuota.  
  
-   Gli elementi della struttura non possono essere dichiarati come `Protected`; i membri di classe possono.  
  
-   Una routine di struttura può gestire eventi solo se è un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedure e solo per mezzo del [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md); qualsiasi routine di classe può gestire gli eventi utilizzando entrambi i [ Gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) parola chiave o `AddHandler` istruzione. Per altre informazioni, vedere [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Le dichiarazioni di variabili di struttura non possono specificare inizializzatori o dimensioni iniziali per le matrici. le dichiarazioni di variabili di classe possono.  
  
-   Le strutture ereditano in modo implicito dal <xref:System.ValueType?displayProperty=nameWithType> classe e non può ereditare da qualsiasi altro tipo; le classi possono ereditare da qualsiasi classe o classi diverso da <xref:System.ValueType?displayProperty=nameWithType>.  
  
-   Strutture non sono ereditabile; le classi sono.  
  
-   Le strutture non sono mai terminate, common language runtime (CLR) non chiama mai il <xref:System.Object.Finalize%2A> metodo in una struttura; le classi vengono terminate dal garbage collector (GC), che chiama <xref:System.Object.Finalize%2A> in una classe quando rileva che non sono presenti riferimenti attivi rimanenti.  
  
-   Una struttura non richiede un costruttore. esegue una classe.  
  
-   Strutture possono disporre di costruttori non condivisi solo se accettano parametri. le classi possono avere li con o senza parametri.  
  
 Ogni struttura dispone di un costruttore pubblico senza parametri. Questo costruttore inizializza gli elementi di dati della struttura sui valori predefiniti. È possibile ridefinire il problema.  
  
## <a name="instances-and-variables"></a>Istanze e variabili  
 Poiché le strutture sono tipi di valore, ogni variabile di struttura in modo permanente è associato a un'istanza di struttura individuale. Tuttavia, le classi sono tipi di riferimento e una variabile oggetto può fare riferimento a diverse istanze di classi in momenti diversi. Questa differenza influisce sull'utilizzo di strutture e classi nei modi seguenti:  
  
-   **inizializzazione.** Una variabile di struttura include implicitamente un'inizializzazione degli elementi utilizzando il costruttore della struttura senza parametri. Pertanto, `Dim s As struct1` equivale a `Dim s As struct1 = New struct1()`.  
  
-   **Assegnazione di variabili.** Quando si assegna una variabile di struttura a un altro o passa un argomento di routine di un'istanza di struttura, i valori correnti di tutti gli elementi variabile vengono copiati nella nuova struttura. Quando si assegna una variabile oggetto a un altro o passarla una variabile oggetto a una routine, viene copiato solo il puntatore di riferimento.  
  
-   **Assegnazione di Nothing.** È possibile assegnare il valore [nulla](../../../../visual-basic/language-reference/nothing.md) a una struttura di variabile, ma l'istanza continua a essere associato alla variabile. È comunque possibile chiamare i relativi metodi e accedere ai relativi elementi di dati, anche se gli elementi variabili vengano reinizializzati dall'assegnazione.  
  
     Al contrario, se si imposta una variabile oggetto `Nothing`, annullarne da qualsiasi istanza di classe e non può accedere ad alcun membro tramite la variabile finché non verrà assegnato un'altra istanza.  
  
-   **Più istanze.** Una variabile oggetto può avere istanze della classe diversi in momenti diversi, e diverse variabili di oggetto possono fare riferimento alla stessa istanza di classe nello stesso momento. Le modifiche apportate ai valori dei membri della classe influiscono su tali membri quando si accede tramite un'altra variabile che puntano alla stessa istanza.  
  
     Elementi della struttura, tuttavia, sono isolati all'interno della relativa istanza. In base ai valori non vengono riflesse in altre variabili di struttura, anche in altre istanze dello stesso `Structure` dichiarazione.  
  
-   **Uguaglianza.** Test di uguaglianza di due strutture deve essere eseguito con un elemento per elemento test. È possono confrontare due variabili di oggetto con il <xref:System.Object.Equals%2A> metodo. <xref:System.Object.Equals%2A> indica se le due variabili puntano alla stessa istanza.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
