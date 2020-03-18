---
title: Compilazione e riutilizzo nelle espressioni regolari
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 3e1dfe8373145286b03e503f038e267ff0d4c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091735"
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Compilazione e riutilizzo nelle espressioni regolari
Se si comprendono le modalità con cui le espressioni regolari vengono compilate dal motore e vengono memorizzate nella cache, è possibile ottimizzare le prestazioni delle applicazioni che fanno ampio uso di espressioni regolari. In questo argomento vengono descritte sia la compilazione che la memorizzazione nella cache.  
  
## <a name="compiled-regular-expressions"></a>Espressioni regolari compilate  
 Per impostazione predefinita, il motore delle espressioni regolari compila un'espressione regolare in una sequenza di istruzioni interne. Si tratta di codici di alto livello che sono diversi da Microsoft intermediate language, o MSIL. Quando il motore esegue un'espressione regolare, interpreta i codici interni.  
  
 Se un oggetto <xref:System.Text.RegularExpressions.Regex> viene costruito con l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>, compila l'espressione regolare in codice MSIL esplicito invece che in istruzioni interne di espressione regolare di alto livello. In questo modo il compilatore JIT di.NET può convertire l'espressione in codice macchina nativo per ottimizzare le prestazioni.  
  
Tuttavia, il codice MSIL generato non può essere scaricato. L'unico modo per scaricare il codice è scaricare un dominio dell'applicazione intero, ovvero, tutto il codice dell'applicazione. In effetti, dopo che un'espressione regolare è stata compilata con l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>, non rilascia mai le risorse usate dall'espressione compilata, anche se l'espressione regolare è stata creata da un oggetto <xref:System.Text.RegularExpressions.Regex>, a sua volta rilasciato in Garbage Collection.  
  
 È necessario prestare attenzione quando si sceglie il numero di espressioni regolari da compilare con l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>, perché si rischia un uso eccessivo di risorse. Se un'applicazione deve usare un numero elevato o illimitato di espressioni regolari, ogni espressione deve essere interpretata, non compilata. Tuttavia, se un numero ridotto di espressioni regolari viene usato ripetutamente, sarà preferibile compilare tali espressioni con <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> per ottenere prestazioni migliori. Un'alternativa consiste nell'usare espressioni regolari precompilate. È possibile compilare tutte le espressioni in una DLL riutilizzabile usando il metodo <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>. Questo evita la dover eseguire la compilazione in fase di esecuzione pur consentendo di usufruire della velocità delle espressioni regolari compilate.  
  
## <a name="the-regular-expressions-cache"></a>La cache delle espressioni regolari  
 Per migliorare le prestazioni, il motore delle espressioni regolari gestisce una cache a livello di applicazione delle espressioni regolari compilate. La cache memorizza i modelli di espressione regolare che vengono usati solo nelle chiamate di metodo statico. I modelli di espressione regolare forniti ai metodi di istanza non vengono memorizzati nella cache. In questo modo si evita la necessità di analizzare nuovamente un'espressione in codice byte di alto livello ogni volta che viene utilizzata.  
  
 Il numero massimo di espressioni regolari memorizzate nella cache è determinato dal valore della proprietà <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>`static` (`Shared` in Visual Basic). Per impostazione predefinita, il motore delle espressioni regolari memorizza nella cache fino a 15 espressioni regolari compilate. Se il numero di espressioni regolari compilate supera la dimensione della cache, l'espressione regolare usata meno di recente viene eliminata e viene memorizzata nella cache la nuova espressione regolare.  
  
 L'applicazione dell'utente può trarre vantaggio delle espressioni regolari precompilate in uno dei due modi seguenti:  
  
- Usando un metodo statico dell'oggetto <xref:System.Text.RegularExpressions.Regex> per definire l'espressione regolare. Se si usa un modello di espressione regolare che è già stato definito in un'altra chiamata di metodo statico, il motore delle espressioni regolari lo recupera dalla cache. In caso contrario il motore compila l'espressione regolare e la aggiunge alla cache.  
  
- Usando ripetutamente un oggetto <xref:System.Text.RegularExpressions.Regex> esistente finché il modello di espressione regolare relativo è necessario.  
  
 A causa del sovraccarico di creazione di istanze di oggetti e di compilazione di espressioni regolari, la creazione e l'eliminazione rapide di numerosi oggetti <xref:System.Text.RegularExpressions.Regex> è un processo molto costoso. Per le applicazioni che usano un numero elevato di espressioni regolari, è possibile ottimizzare le prestazioni con chiamate a metodi statici `Regex` e aumentando eventualmente la dimensione della cache delle espressioni regolari.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni regolari .NET](../../../docs/standard/base-types/regular-expressions.md)
