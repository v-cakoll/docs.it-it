---
title: Interfacce
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, interfaces
- interfaces [Visual Basic], Visual Basic
- interfaces
- interfaces [Visual Basic]
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
ms.openlocfilehash: 90f8e5d4eb7bb6b367ee5ffd4a4323097c6bde9c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405043"
---
# <a name="interfaces-visual-basic"></a>Interfacce (Visual Basic)
Le *interfacce* definiscono le proprietà, i metodi e gli eventi che le classi possono implementare. Le interfacce consentono di definire funzionalità come piccoli gruppi di proprietà, metodi ed eventi strettamente correlati fra loro. In questo modo si riducono i problemi di compatibilità, grazie alla possibilità di sviluppare implementazioni migliorate per le interfacce senza compromettere il codice esistente. È possibile aggiungere nuove funzionalità in qualsiasi momento, sviluppando interfacce e implementazioni aggiuntive.  
  
 Le interfacce offrono anche altri vantaggi rispetto all'ereditarietà di classe:  
  
- Sono più adatte a situazioni in cui l'applicazione richiede molti tipi di oggetti anche non correlati per fornire determinate funzionalità.  
  
- Sono più flessibili delle classi base perché consentono di definire un'unica implementazione in grado di implementare più interfacce.  
  
- Sono più adatte nelle situazioni in cui non è necessario ereditare l'implementazione da una classe base.  
  
- Sono utili quando non è possibile usare l'ereditarietà di classe. Le strutture, ad esempio, non possono ereditare dalle classi, ma possono implementare interfacce.  
  
## <a name="declaring-interfaces"></a>Dichiarazione di interfacce  
 Le definizioni di interfaccia sono racchiuse tra istruzioni `Interface` e `End Interface`. Subito dopo l'istruzione `Interface` è possibile aggiungere un'istruzione `Inherits` facoltativa in cui sono elencate una o più interfacce ereditate. Le istruzioni `Inherits` devono precedere qualsiasi altra istruzione della dichiarazione, ad eccezione dei commenti. Le restanti istruzioni della definizione di interfaccia dovrebbero essere istruzioni `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure` e `Enum`. Le interfacce non possono contenere codice di implementazione o istruzioni ad esso associate, come `End Sub` o `End Property`.  
  
 Per impostazione predefinita, in uno spazio dei nomi le istruzioni di interfaccia sono `Friend`, ma possono anche essere dichiarate in modo esplicito come `Public` o `Friend`. Per impostazione predefinita, le interfacce definite all'interno di classi, moduli, interfacce e strutture sono `Public`, ma possono anche essere dichiarate in modo esplicito come `Public`, `Friend`, `Protected` o `Private`.  
  
> [!NOTE]
> La parola chiave `Shadows` può essere applicata a tutti i membri dell'interfaccia. La parola chiave `Overloads` può essere applicata alle istruzioni `Sub`, `Function` e `Property` dichiarate in una definizione di interfaccia. Inoltre, le istruzioni `Property` possono includere il modificatore `Default`, `ReadOnly` o `WriteOnly`. Non sono consentiti altri modificatori, come `Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride` o `Overridable`. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Il codice riportato di seguito, ad esempio, consente di definire un'interfaccia con una funzione, una proprietà e un evento.  
  
 [!code-vb[VbVbalrOOP#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#17)]  
  
## <a name="implementing-interfaces"></a>Implementazione di interfacce  
 La parola riservata Visual Basic `Implements` viene usata in due modi. L'istruzione `Implements` indica che una classe o una struttura implementa un'interfaccia. La parola chiave `Implements` indica che un membro di classe o di struttura implementa un membro di interfaccia specifico.  
  
### <a name="implements-statement"></a>Istruzione Implements  
 Se una classe o una struttura implementa una o più interfacce, deve includere l'istruzione `Implements` immediatamente dopo l'istruzione `Class` o `Structure`. L'istruzione `Implements` richiede un elenco separato da virgole di interfacce implementate da una classe. La classe o la struttura deve implementare tutti i membri di interfaccia mediante la parola chiave `Implements`.  
  
### <a name="implements-keyword"></a>Parola chiave Implements  
 La parola chiave `Implements` richiede un elenco separato da virgole di membri di interfaccia da implementare. In genere viene specificato un solo membro di interfaccia, anche se è possibile specificarne diversi. La specifica di un membro di interfaccia è composta dal nome dell'interfaccia, che è necessario includere in un'istruzione Implements all'interno della classe, seguito da un punto, quindi dal nome della funzione, della proprietà o dell'evento da implementare. Il nome di un membro che implementa un membro di interfaccia può usare qualsiasi identificatore valido e non è limitato alla `InterfaceName_MethodName` convenzione usata nelle versioni precedenti di Visual Basic.  
  
 Il codice seguente, ad esempio, illustra come dichiarare una subroutine denominata `Sub1` che implementa un metodo di un'interfaccia:  
  
 [!code-vb[VbVbalrOOP#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#69)]  
  
 È necessario che i tipi di parametro e i tipi restituiti del membro che esegue l'implementazione corrispondano alla proprietà dell'interfaccia o alla dichiarazione del membro nell'interfaccia. Per implementare un elemento di un'interfaccia in genere si usa un membro con lo stesso nome dell'interfaccia, come illustrato nell'esempio precedente.  
  
 Per dichiarare l'implementazione di un metodo di interfaccia è possibile usare qualsiasi attributo valido per le dichiarazioni dei metodi di istanza, tra cui `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default` e `Static`. L'attributo `Shared` non è valido in quanto definisce una classe anziché un metodo di istanza.  
  
 Usando `Implements` è possibile scrivere un unico metodo che implementa più metodi definiti in un'interfaccia, come nell'esempio seguente:  
  
 [!code-vb[VbVbalrOOP#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#70)]  
  
 Per implementare un membro di interfaccia, è possibile usare un membro privato. Quando un membro privato implementa un membro di un'interfaccia, diventa disponibile tramite l'interfaccia anche se non è disponibile direttamente sulle variabili oggetto della classe.  
  
### <a name="interface-implementation-examples"></a>Esempi di implementazione dell'interfaccia  
 È necessario che le classi che implementano un'interfaccia ne implementino tutte le proprietà, i metodi e gli eventi.  
  
 L'esempio seguente definisce due interfacce. La seconda interfaccia, `Interface2`, eredita `Interface1` e definisce una proprietà e un metodo aggiuntivi.  
  
 [!code-vb[VbVbalrOOP#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#39)]  
  
 L'esempio che segue implementa `Interface1`, l'interfaccia definita nell'esempio precedente:  
  
 [!code-vb[VbVbalrOOP#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#40)]  
  
 L'ultimo esempio implementa `Interface2`, incluso un metodo ereditato da `Interface1`:  
  
 [!code-vb[VbVbalrOOP#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#41)]  
  
 È possibile implementare una proprietà ReadOnly usando una proprietà ReadWrite (in altri termini, non è necessario dichiararla ReadOnly nella classe di implementazione).  L'implementazione di un'interfaccia consente di implementare almeno i membri dichiarati dall'interfaccia, ma è possibile offrire maggiori funzionalità, ad esempio rendendo la proprietà accessibile in scrittura.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura dettagliata: Creazione e implementazione di interfacce](walkthrough-creating-and-implementing-interfaces.md)|Fornisce una procedura dettagliata che illustra il processo di definizione e implementazione di interfacce personalizzate.|  
|[Varianza nelle interfacce generiche](../../concepts/covariance-contravariance/variance-in-generic-interfaces.md)|Illustra la covarianza e la controvarianza nelle interfacce generiche e fornisce un elenco di interfacce generiche variant in .NET Framework.|
