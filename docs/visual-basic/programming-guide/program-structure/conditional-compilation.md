---
title: Compilazione condizionale in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 0767b2054697735c3f5190b6e30a2c80ea5288bc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775713"
---
# <a name="conditional-compilation-in-visual-basic"></a>Compilazione condizionale in Visual Basic
Nella *compilazione condizionale*, determinati blocchi di codice in un programma vengono compilati in modo selettivo mentre altri vengono ignorati.  
  
 È ad esempio possibile scrivere istruzioni di debug che confrontano la velocità di approcci diversi alla stessa attività di programmazione oppure è possibile localizzare un'applicazione per più linguaggi. Le istruzioni di compilazione condizionale sono progettate per essere eseguite in fase di compilazione, non in fase di esecuzione.  
  
 È possibile indicare blocchi di codice da compilare in modo condizionale con la direttiva `#If...Then...#Else`. Ad esempio, per creare versioni in francese e in lingua tedesca della stessa applicazione dallo stesso codice sorgente, è possibile incorporare segmenti di codice specifici della piattaforma nelle istruzioni `#If...Then` usando le costanti predefinite `FrenchVersion` e `GermanVersion`. Nell'esempio seguente viene illustrato come:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 Se si imposta il valore della costante `FrenchVersion` compilazione condizionale su `True` in fase di compilazione, viene compilato il codice condizionale per la versione francese. Se si imposta il valore della costante `GermanVersion` su `True`, il compilatore utilizzerà la versione tedesca. Se nessuno dei due è impostato su `True`, viene eseguito il codice nell'ultimo blocco di `Else`.  
  
> [!NOTE]
> Il completamento automatico non funzionerà quando si modifica il codice e si usano le direttive di compilazione condizionale se il codice non fa parte del ramo corrente.  
  
## <a name="declaring-conditional-compilation-constants"></a>Dichiarazione di costanti di compilazione condizionale  
 È possibile impostare le costanti di compilazione condizionale in uno dei tre modi seguenti:  
  
- In **Progettazione progetti**  
  
- Dalla riga di comando quando si usa il compilatore da riga di comando  
  
- Nel codice  
  
 Le costanti di compilazione condizionale hanno un ambito speciale e non è possibile accedervi dal codice standard. L'ambito di una costante di compilazione condizionale dipende dal modo in cui è impostato. La tabella seguente elenca l'ambito delle costanti dichiarate usando ognuno dei tre modi descritti in precedenza.  
  
|Impostazione della costante|Ambito della costante|  
|---|---|  
|**Progettazione progetti**|Pubblico in tutti i file del progetto|  
|Riga di comando|Pubblico per tutti i file passati al compilatore da riga di comando|  
|istruzione `#Const` nel codice|Privato per il file in cui è dichiarato|  
  
|Per impostare costanti in Progettazione progetti|  
|---|  
|-Prima di creare il file eseguibile, impostare costanti in **Progettazione progetti** attenendosi alla procedura descritta in [gestione delle proprietà del progetto e della soluzione](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Per impostare costanti dalla riga di comando|  
|---|  
|-Usare l'opzione **-d** per immettere le costanti di compilazione condizionale, come nell'esempio seguente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Non è necessario alcuno spazio tra l'opzione **-d** e la prima costante. Per ulteriori informazioni, vedere [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Le dichiarazioni della riga di comando eseguono l'override delle dichiarazioni immesse in **Progettazione progetti**, ma non le cancellano. Gli argomenti impostati in **Progettazione progetti** rimangono attivi per le compilazioni successive.<br />     Quando si scrivono costanti nel codice, non sono presenti regole rigide per la loro posizione, poiché il relativo ambito è l'intero modulo in cui sono dichiarati.|  
  
|Per impostare costanti nel codice|  
|---|  
|: Inserire le costanti nel blocco di dichiarazione del modulo in cui vengono usate. Ciò consente di organizzare e semplificare la lettura del codice.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|---|---|  
|[Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Fornisce suggerimenti per semplificare la lettura e la gestione del codice.|  
  
## <a name="reference"></a>Reference  
 [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
