---
title: L'accesso a una proprietà predefinita è ambiguo tra i membri di interfaccia ereditati '<defaultpropertyname>' dell'interfaccia '<interfacename1>' e '<defaultpropertyname>' dell'interfaccia '<interfacename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: a36cfe8e5496bbfd1941afa8a46086491ae96a2a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512743"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>L'accesso alla proprietà predefinita è ambiguo tra i membri\<di interfaccia ereditati ' defaultpropertyname\<>' dell'interfaccia '\<nomeinterfaccia1 >' è defaultpropertyname\< >' dell'interfaccia ' nomeinterfaccia2 >'

Un'interfaccia eredita da due interfacce, ognuna delle quali dichiara una proprietà predefinita con lo stesso nome. Il compilatore non può risolvere un accesso a questa proprietà predefinita senza qualifica. Questa condizione è illustrata nell'esempio seguente.

```vb
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

Quando si specifica `testObj(1)`, il compilatore tenta di risolverlo nella proprietà predefinita. Tuttavia, esistono due possibili proprietà predefinite a causa delle interfacce ereditate, quindi il compilatore segnala l'errore.

**ID errore:** BC30686

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Evitare di ereditare i membri con lo stesso nome. Nell'esempio precedente, se `testObj` non necessita di alcun membro di, `Iface2`ad esempio,, dichiararlo come segue:

  ```vb
  Dim testObj As Iface1
  ```

  \-oppure-

- Implementare l'interfaccia di ereditarietà in una classe. È quindi possibile implementare ognuna delle proprietà ereditate con nomi diversi. Tuttavia, solo uno di essi può essere la proprietà predefinita della classe di implementazione. Questa condizione è illustrata nell'esempio seguente.

  ```vb
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
