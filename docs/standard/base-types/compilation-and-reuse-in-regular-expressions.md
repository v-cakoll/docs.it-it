---
title: Compilazione e riutilizzo nelle espressioni regolari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 76acdf2d0d2f7805ec78ea44136bfc63441b9bc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Compilazione e riutilizzo nelle espressioni regolari
Se si comprendono le modalità con cui le espressioni regolari vengono compilate dal motore e vengono memorizzate nella cache, è possibile ottimizzare le prestazioni delle applicazioni che fanno ampio uso di espressioni regolari. In questo argomento vengono descritte sia la compilazione che la memorizzazione nella cache.  
  
## <a name="compiled-regular-expressions"></a>Espressioni regolari compilate  
 Per impostazione predefinita, il motore delle espressioni regolari compila un'espressione regolare in una sequenza di istruzioni interne. Si tratta di codici di alto livello che sono diversi da Microsoft intermediate language, o MSIL. Quando il motore esegue un'espressione regolare, interpreta i codici interni.  
  
 Se un <xref:System.Text.RegularExpressions.Regex> oggetto viene costruito con la <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> opzione, verrà compilata l'espressione regolare per il codice MSIL esplicito invece di istruzioni di espressione regolare di alto livello interno. In questo modo il compilatore JIT di.NET può convertire l'espressione in codice macchina nativo per ottimizzare le prestazioni.  
  
Tuttavia, il codice MSIL generato non può essere scaricato. L'unico modo per scaricare il codice è scaricare un dominio dell'applicazione intero, ovvero, tutto il codice dell'applicazione. In effetti, una volta compilata un'espressione regolare con la <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> opzione, non rilascia le risorse usate dall'espressione compilata, anche se l'espressione regolare è stata creata da un <xref:System.Text.RegularExpressions.Regex> oggetto che è a sua volta rilasciata a garbage collection.  
  
 È necessario prestare attenzione limitare il numero di espressioni regolari che si compila con il <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> opzione per evitare un utilizzo eccessivo di risorse. Se un'applicazione deve usare un numero elevato o illimitato di espressioni regolari, ogni espressione deve essere interpretata, non compilata. Tuttavia, se un numero ridotto di espressioni regolari utilizzato ripetutamente, sarà preferibile compilarle con <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> per ottenere prestazioni migliori. Un'alternativa consiste nell'utilizzare espressioni regolari precompilate. È possibile compilare tutte le espressioni in una DLL riutilizzabile tramite il <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> metodo. Questo evita la necessità di compilare in fase di esecuzione pur consentendo di usufruire della velocità delle espressioni regolari compilate.  
  
## <a name="the-regular-expressions-cache"></a>La cache delle espressioni regolari  
 Per migliorare le prestazioni, il motore delle espressioni regolari gestisce una cache a livello di applicazione delle espressioni regolari compilate. La cache memorizza i modelli di espressione regolare che vengono usati solo nelle chiamate di metodo statico. I modelli di espressione regolare specificati per i metodi di istanza non vengono memorizzati. Questo evita la necessità di analizzare nuovamente un'espressione nel codice di alto livello ogni volta che viene usata.  
  
 Il numero massimo di espressioni regolari memorizzate nella cache è determinato dal valore della `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> proprietà. Per impostazione predefinita, il motore delle espressioni regolari memorizza nella cache fino a 15 espressioni regolari compilate. Se il numero di espressioni regolari compilate supera la dimensione della cache, l'espressione regolare usata meno di recente viene eliminata e viene memorizzata nella cache la nuova espressione regolare.  
  
 L'applicazione dell'utente può trarre vantaggio delle espressioni regolari precompilate in uno dei due modi seguenti:  
  
-   Utilizzando un metodo statico del <xref:System.Text.RegularExpressions.Regex> oggetto per definire l'espressione regolare. Se si usa un modello di espressione regolare che è già stato definito in un'altra chiamata di metodo statico, il motore delle espressioni regolari lo recupera dalla cache. In caso contrario il motore compila l'espressione regolare e la aggiunge alla cache.  
  
-   Riutilizzando un'esistente <xref:System.Text.RegularExpressions.Regex> oggetto fino a quando il criterio di espressione regolare è necessario.  
  
 A causa dell'overhead di istanze di oggetti e compilazione di espressioni regolari, creazione ed eliminazione rapidamente numerose <xref:System.Text.RegularExpressions.Regex> oggetti è un processo molto costoso. Per le applicazioni che utilizzano un numero elevato di espressioni regolari, è possibile ottimizzare le prestazioni mediante chiamate static `Regex` metodi e possibilmente aumentando le dimensioni della cache di espressione regolare.  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari di .NET](../../../docs/standard/base-types/regular-expressions.md)
