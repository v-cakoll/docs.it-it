---
title: Utilizzare il modello di area di lavoro di .NET Compiler Platform SDK
description: Questa panoramica consente di conoscere i tipi usati per eseguire query sull'area di lavoro e i progetti per il codice e modificarli.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: a2e69129a869707eaec3516310a72f1fc918ca26
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346919"
---
# <a name="work-with-a-workspace"></a>Utilizzare un'area di lavoro

Il livello delle **aree di lavoro** rappresenta il punto di partenza per eseguire l'analisi del codice e il refactoring su intere soluzioni. All'interno di questo livello, l'API Workspace consente di organizzare tutte le informazioni sui progetti in una soluzione in unico modello a oggetti, offrendo accesso diretto ai modelli a oggetti del livello del compilatore, come il testo di origine, gli alberi di sintassi, i modelli semantici e le compilazioni, senza la necessità di analizzare file, configurare opzioni o gestire le dipendenze all'interno dei progetti. 

Gli ambienti host, ad esempio un ambiente IDE, forniscono un'area di lavoro corrispondente alla soluzione aperta. È anche possibile usare questo modello al di fuori di un ambiente IDE caricando semplicemente un file di soluzione.

## <a name="workspace"></a>Area di lavoro

Un'area di lavoro è una rappresentazione attiva della soluzione come una raccolta di progetti, ognuno con una raccolta di documenti. Un'area di lavoro è in genere associata a un ambiente host che cambia continuamente durante la digitazione o la modifica delle proprietà. 

<xref:Microsoft.CodeAnalysis.Workspace> consente l'accesso al modello corrente della soluzione. Quando si verifica una modifica nell'ambiente host, l'area di lavoro genera eventi corrispondenti e la proprietà <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> viene aggiornata. Ad esempio, quando l'utente digita in un editor di testo corrispondente a uno dei documenti di origine, l'area di lavoro usa un evento per segnalare che il modello generale della soluzione è stato modificato e quale documento è stato modificato. È quindi possibile rispondere a queste modifiche analizzando il nuovo modello per verificarne la correttezza, evidenziando le aree significative o suggerendo una modifica del codice. 

È anche possibile creare aree di lavoro autonome disconnesse dall'ambiente host o usate in un'applicazione che non dispone di alcun ambiente host.

## <a name="solutions-projects-documents"></a>Soluzioni, progetti, documenti

Anche se un'area di lavoro può cambiare ogni volta che viene premuto un tasto, è possibile utilizzare il modello della soluzione in isolamento. 

Una soluzione è un modello non modificabile dei progetti e dei documenti. Ciò significa che il modello può essere condiviso senza causare blocchi o duplicati. Dopo aver ottenuto un'istanza della soluzione dalla proprietà <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType>, tale istanza non verrà mai modificata. Tuttavia, come nel caso degli alberi della sintassi e delle compilazioni, è possibile modificare le soluzioni creando nuove istanze in base alle soluzioni esistenti e a modifiche specifiche. Per fare in modo che l'area di lavoro rispecchi le modifiche, è necessario applicare in modo esplicito la soluzione modificata nell'area di lavoro.

Un progetto fa parte del modello di soluzione globale non modificabile e rappresenta tutti i documenti di codice sorgente, le opzioni di analisi e compilazione e sia i riferimenti ad assembly che i riferimenti da progetto a progetto. Da un progetto è possibile accedere alla compilazione corrispondente senza la necessità di determinare le dipendenze del progetto o di analizzare i file di origine.

Anche un documento è una parte del modello di soluzione globale non modificabile e rappresenta un singolo file di origine da cui si può accedere al testo del file, all'albero della sintassi e al modello semantico.

Il diagramma seguente è una rappresentazione delle correlazioni tra l'area di lavoro, l'ambiente host, gli strumenti e le modalità di modifica.

![Relazioni tra i diversi elementi di un'area di lavoro che contiene progetti e file di origine](media/work-with-workspace/workspace-obj-relations.png)

## <a name="summary"></a>Riepilogo

Roslyn espone un set di API del compilatore e API delle aree di lavoro che forniscono informazioni dettagliate sul codice sorgente, in modo del tutto fedele con i linguaggi C# e Visual Basic.  Con .NET Compiler Platform SDK si riduce drasticamente la barriera all'ingresso per la creazione di strumenti e applicazioni incentrati su codice. Consente di creare numerose opportunità di innovazione in aree quali la metaprogrammazione, la generazione e la trasformazione del codice, l' C# uso interattivo dei linguaggi e Visual Basic e l' C# incorporamento di e Visual Basic in linguaggi specifici del dominio.  
