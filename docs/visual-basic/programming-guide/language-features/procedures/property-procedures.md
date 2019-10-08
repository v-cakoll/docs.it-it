---
title: Routine Property (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: f3b57ae45815fbd91cad17cddbed4d01037eb92f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002096"
---
# <a name="property-procedures-visual-basic"></a>Routine Property (Visual Basic)
Una routine di proprietà è una serie di istruzioni Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, una classe o una struttura. Le routine di proprietà sono note anche come *funzioni di accesso alle proprietà*.  
  
 Visual Basic fornisce le routine di proprietà seguenti:  
  
- Una routine `Get` restituisce il valore di una proprietà. Viene chiamato quando si accede alla proprietà in un'espressione.  
  
- Una procedura `Set` imposta una proprietà su un valore, incluso un riferimento a un oggetto. Viene chiamato quando si assegna un valore alla proprietà.  
  
 In genere, le routine di proprietà vengono definite in coppie, usando le istruzioni `Get` e `Set`, ma è possibile definire una sola procedura solo se la proprietà è di sola lettura ([istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o di sola scrittura ([istruzione set](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 È possibile omettere la procedura `Get` e `Set` quando si usa una proprietà implementata automaticamente. Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).  
  
 È possibile definire le proprietà in classi, strutture e moduli. Per impostazione predefinita, le proprietà sono `Public`, ovvero possono essere chiamate da qualsiasi punto dell'applicazione in grado di accedere al contenitore della proprietà.  
  
 Per un confronto tra proprietà e variabili, vedere [differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 Una proprietà viene definita da un blocco di codice racchiuso tra l' [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md) e l'istruzione `End Property`. All'interno di questo blocco ogni routine di proprietà viene visualizzata come un blocco interno racchiuso tra un'istruzione di dichiarazione (`Get` o `Set`) e la dichiarazione `End` corrispondente.  
  
 La sintassi per la dichiarazione di una proprietà e delle relative procedure è la seguente:  
  
```vb  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 Il `Modifiers` può specificare il livello di accesso e le informazioni relative all'overload, all'override, alla condivisione e allo shadowing, nonché se la proprietà è di sola lettura o di sola scrittura. Il `AccessLevel` nella procedura `Get` o `Set` può essere qualsiasi livello più restrittivo del livello di accesso specificato per la proprietà stessa. Per ulteriori informazioni, vedere [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Il tipo di dati e il livello di accesso dell'entità di una proprietà sono definiti nell'istruzione `Property`, non nelle routine della proprietà. Una proprietà può avere un solo tipo di dati. Non è ad esempio possibile definire una proprietà per archiviare un valore `Decimal`, ma recuperare un valore `Double`.  
  
### <a name="access-level"></a>Livello di accesso  
 Tuttavia, è possibile definire un livello di accesso principale per una proprietà e limitare ulteriormente il livello di accesso in una delle relative routine di proprietà. Ad esempio, è possibile definire una proprietà `Public` e quindi definire una procedura `Private Set`. La procedura `Get` rimane `Public`. È possibile modificare il livello di accesso solo in una delle routine di una proprietà ed è possibile renderlo solo più restrittivo del livello di accesso principale. Per altre informazioni, vedere [Procedura: Dichiarare una proprietà con livelli di accesso misti @ no__t-0.  
  
## <a name="parameter-declaration"></a>Dichiarazione di parametro  
 Ogni parametro viene dichiarato in modo analogo alle [procedure secondarie](./sub-procedures.md), con la differenza che il meccanismo di passaggio deve essere `ByVal`.  
  
 La sintassi per ogni parametro nell'elenco di parametri è la seguente:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è la seguente:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Valore proprietà  
 In una procedura `Get`, il valore restituito viene fornito all'espressione chiamante come valore della proprietà.  
  
 In una procedura `Set`, il nuovo valore della proprietà viene passato al parametro dell'istruzione `Set`. Se si dichiara in modo esplicito un parametro, è necessario dichiararlo con lo stesso tipo di dati della proprietà. Se non si dichiara un parametro, il compilatore usa il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Per richiamare una routine di proprietà in modo implicito, è necessario fare riferimento alla proprietà. Usare il nome della proprietà nello stesso modo in cui si usa il nome di una variabile, ad eccezione del fatto che è necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi. Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.  
  
 La sintassi per una chiamata implicita a una procedura `Set` è la seguente:  
  
 `propertyname[(argumentlist)] = expression`  
  
 La sintassi per una chiamata implicita a una procedura `Get` è la seguente:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione della dichiarazione e della chiamata  
 Nella proprietà seguente viene archiviato un nome completo come due nomi costitutivi, il primo nome e il cognome. Quando il codice chiamante legge `fullName`, la procedura `Get` combina i due nomi costitutivi e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, la procedura `Set` tenta di suddividerla in due nomi costitutivi. Se non trova uno spazio, lo archivia come nome.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Nell'esempio seguente vengono illustrate le chiamate tipiche alle routine di proprietà di `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Function](./function-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà @ no__t-0
- [Procedura: Chiamare una routine di proprietà @ no__t-0
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic @ no__t-0
- [Procedura: Inserire un valore in una proprietà @ no__t-0
- [Procedura: Ottenere un valore da una proprietà @ no__t-0
