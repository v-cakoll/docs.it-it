---
title: L'accesso a una proprietà predefinita è ambiguo tra i membri di interfaccia ereditati '<defaultpropertyname>' dell'interfaccia '<interfacename1>' e '<defaultpropertyname>' dell'interfaccia '<interfacename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5f058c8e7d480b9145452ae85f186a6ac2ed0d56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803730"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>Accesso alla proprietà predefinita è ambiguo tra i membri di interfaccia ereditati\<defaultpropertyname >' dell'interfaccia '\<interfacename1 >' e '\<defaultpropertyname >' dell'interfaccia '\< interfacename2 >'
Un'interfaccia eredita da due interfacce, ognuno dei quali dichiara una proprietà predefinita con lo stesso nome. Il compilatore non è possibile risolvere un accesso a questa proprietà predefinito senza qualifica. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 Quando si specifica `testObj(1)`, il compilatore cerca di risolvere il problema per la proprietà predefinita. Tuttavia, esistono due possibili proprietà predefinite a causa di interfacce ereditate, il compilatore segnala questo errore.  
  
 **ID errore:** BC30686  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Evitare di ereditare tutti i membri con lo stesso nome. Nell'esempio precedente, se `testObj` non è necessario uno qualsiasi dei membri di, ad esempio, `Iface2`, dichiararla come indicato di seguito:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     -oppure-  
  
-   Implementare l'interfaccia che eredita in una classe. È quindi possibile implementare ognuna delle proprietà ereditate con nomi diversi. Tuttavia, solo uno di essi può essere la proprietà predefinita della classe di implementazione. Questa condizione è illustrata nell'esempio seguente.  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
