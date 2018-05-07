---
title: Compilazione condizionale in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 496df36242c6b43e7e3ec94ce675d11177e8b466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="conditional-compilation-in-visual-basic"></a>Compilazione condizionale in Visual Basic
In *compilazione condizionale*, determinati blocchi di codice in un programma vengono compilati in modo selettivo, mentre gli altri vengono ignorati.  
  
 Ad esempio, è possibile scrivere il debug di istruzioni che confrontano la velocità di diversi approcci per la stessa attività di programmazione o si desidera localizzare un'applicazione in più lingue. Le istruzioni di compilazione condizionale sono progettate per l'esecuzione durante la fase di compilazione, non in fase di esecuzione.  
  
 Per indicare i blocchi di codice da compilare in modo condizionale con il `#If...Then...#Else` direttiva. Ad esempio, francese e tedesco creare versioni della stessa applicazione dallo stesso codice sorgente, incorporare per segmenti di codice specifico della piattaforma in `#If...Then` istruzioni che utilizzano costanti predefinite `FrenchVersion` e `GermanVersion`. Nell'esempio seguente viene illustrato come:  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 Se si imposta il valore di `FrenchVersion` costante di compilazione condizionale a `True` in fase di compilazione, viene compilato il codice condizionale per la versione francese. Se si imposta il valore di `GermanVersion` costante da `True`, il compilatore utilizza la versione tedesca. Se non è impostata su `True`, il codice negli ultimi `Else` blocco viene eseguito.  
  
> [!NOTE]
>  Completamento automatico verrà non funziona quando la modifica del codice e l'utilizzo di direttive di compilazione condizionale se il codice non fa parte del ramo corrente.  
  
## <a name="declaring-conditional-compilation-constants"></a>Dichiarazione di costanti di compilazione condizionale  
 È possibile impostare le costanti di compilazione condizionale in uno dei tre modi:  
  
-   Nel **Progettazione progetti**  
  
-   Nella riga di comando quando si utilizza il compilatore della riga di comando  
  
-   Nel codice  
  
 Costanti di compilazione condizionale hanno un ambito speciale e non sono accessibili dal codice standard. L'ambito di una costante di compilazione condizionale dipende dal modo in cui è impostata. La tabella seguente elenca l'ambito delle costanti dichiarate utilizzando ciascuna delle tre modalità menzionate sopra.  
  
|Configurazione (costante)|Ambito di costante|  
|---|---|  
|**Progettazione progetti**|Pubblica a tutti i file nel progetto|  
|Riga di comando|Pubblica a tutti i file passati al compilatore da riga di comando|  
|`#Const` istruzione nel codice|Private per il file in cui è dichiarato|  
  
|Per impostare le costanti in Progettazione progetti|  
|---|  
|-Prima di creare il file eseguibile, impostare le costanti **progettazione** seguendo i passaggi forniti nella [gestione dei progetti e le proprietà di soluzione](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Per impostare le costanti nella riga di comando|  
|---|  
|-Utilizzare il **/d** commutatore per inserire le costanti di compilazione condizionale, come nell'esempio seguente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Non è necessario tra spazio il **/d** commutatore e la prima costante. Per ulteriori informazioni, vedere [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Le dichiarazioni della riga di comando eseguire l'override delle dichiarazioni inserite nella **progettazione**, ma non le cancellano. Impostare gli argomenti **progettazione** rimangono valide per le compilazioni successive.<br />     Quando si scrivono costanti nel codice stesso, non esistono strict regole per il posizionamento, poiché l'ambito è l'intero modulo in cui sono dichiarati.|  
  
|Per impostare le costanti nel codice|  
|---|  
|-Inserire le costanti nel blocco di dichiarazione del modulo in cui vengono utilizzati. Consente di mantenere il codice organizzati e facili da leggere.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|---|---|  
|[Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Vengono forniti suggerimenti per rendere il codice facili da leggere e gestire.|  
  
## <a name="reference"></a>Riferimenti  
 [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
