---
title: Utilizzare il modello semantico di .NET Compiler Platform SDK
description: Questa panoramica consente di conoscere i tipi usati per comprendere e modificare il modello semantico del codice.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: 8575988cd98a4c0ba3f24107788f065f7472f55d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156935"
---
# <a name="work-with-semantics"></a>Utilizzare la semantica

Gli [alberi della sintassi](work-with-syntax.md) rappresentano la struttura lessicale e sintattica del codice sorgente. Anche se queste informazioni da sole sono sufficienti per descrivere tutte le dichiarazioni e la logica nell'origine, non bastano per identificare gli elementi a cui viene fatto riferimento. Un nome può rappresentare:

- Un tipo
- Un campo
- Un metodo
- Una variabile locale

Anche se ognuno di questi elementi è univoco, per determinare l'elemento a cui un identificatore fa effettivamente riferimento è spesso necessaria una conoscenza approfondita delle regole del linguaggio.

Sono presenti elementi di programma rappresentati nel codice sorgente e i programmi possono anche fare riferimento a librerie compilate in precedenza, incluse in file di assembly. Anche se per gli assembly non è disponibile codice sorgente, e pertanto alcun nodo o albero di sintassi, i programmi possono comunque fare riferimento a elementi contenuti in assembly.

Per queste attività, è necessario il **modello semantico**.

Oltre a un modello sintattico del codice sorgente, un modello semantico incapsula le regole del linguaggio, offrendo un modo semplice per abbinare correttamente gli identificatori all'elemento di programma corretto a cui si fa riferimento.

## <a name="compilation"></a>Compilazione

Una compilazione è una rappresentazione di tutti gli elementi necessari per compilare un programma C# o Visual Basic, che include tutti i riferimenti ad assembly, le opzioni del compilatore e i file di origine.

Dato che tutte queste informazioni sono raccolte in un'unica posizione, gli elementi contenuti nel codice sorgente possono essere descritti in maggiore dettaglio. La compilazione rappresenta come simbolo ogni tipo, membro o variabile dichiarati. La compilazione contiene svariati metodi che consentono di trovare e associare i simboli che sono stati dichiarati nel codice sorgente o importati come metadati da un assembly.

Analogamente agli alberi della sintassi, le compilazioni non sono modificabili. Dopo aver creato una compilazione, non può essere modificata dall'utente o da altri utenti con cui è condivisa. Tuttavia, è possibile creare una nuova compilazione da una compilazione esistente, specificano una modifica con questa operazione. Ad esempio, è possibile creare una compilazione che è uguale in tutto e per tutto a una compilazione esistente, tranne per l'aggiunta di un file di origine o un riferimento ad assembly aggiuntivo.

## <a name="symbols"></a>Symbols

Un simbolo rappresenta un elemento distinto dichiarato dal codice sorgente o importato da un assembly come metadati. Ogni spazio dei nomi, tipo, metodo, proprietà, campo, evento, parametro o variabile locale è rappresentato da un simbolo.

Un'ampia gamma di metodi e proprietà per il tipo <xref:Microsoft.CodeAnalysis.Compilation> sono utili per trovare i simboli. Ad esempio, è possibile trovare un simbolo per un tipo dichiarato in base al nome dei metadati comuni. È anche possibile accedere all'intera tabella dei simboli come albero dei simboli con lo spazio dei nomi globale come radice.

I simboli contengono anche informazioni aggiuntive che il compilatore determina dall'origine o dai metadati, come altri simboli di riferimento. Ogni tipo di simbolo è rappresentato da un'interfaccia separata derivata da <xref:Microsoft.CodeAnalysis.ISymbol>, ognuna con metodi e proprietà propri che riportano in dettaglio le informazioni raccolte al compilatore. Molte di queste proprietà fanno riferimento direttamente ad altri simboli. Ad esempio, la proprietà <xref:Microsoft.CodeAnalysis.IMethodSymbol.ReturnType?displayProperty=nameWithType> indica il simbolo di tipo effettivo a cui fa riferimento la dichiarazione del metodo.

I simboli presentano una rappresentazione comune di spazi dei nomi, tipi e membri, tra il codice sorgente e i metadati. Ad esempio, un metodo dichiarato nel codice sorgente e un metodo importato dai metadati sono rappresentati entrambi da un <xref:Microsoft.CodeAnalysis.IMethodSymbol> con le stesse proprietà.

I simboli sono concettualmente simili al sistema di tipi CLR, come rappresentato dall'API <xref:System.Reflection>, ma sono più completi perché non si limitano alla modellazione dei tipi. Gli spazi dei nomi, le variabili locali e le etichette sono tutti simboli. Inoltre, i simboli sono una rappresentazione di concetti del linguaggio e non di concetti CLR. Esistono molte sovrapposizioni, ma anche molte differenze significative. Ad esempio, un metodo iteratore in C# o Visual Basic è un unico simbolo. Tuttavia, quando il metodo iteratore viene convertito in metadati CLR, corrisponde a un tipo e più metodi.

## <a name="semantic-model"></a>Modello semantico

Un modello semantico rappresenta tutte le informazioni semantiche per un singolo file di origine. È possibile usarlo per individuare quanto segue:

- I simboli a cui si fa riferimento in una posizione specifica nell'origine.
- Il tipo risultante di qualsiasi espressione.
- Tutti i dati diagnostici, ovvero errori e avvisi.
- Il flusso delle variabili in ingresso e in uscita dalle aree di origine.
- Risposte a domande più speculative.
