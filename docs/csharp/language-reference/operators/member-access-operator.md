---
title: . - operatore - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836461"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1c20e-103">.</span><span class="sxs-lookup"><span data-stu-id="1c20e-103">.</span></span> <span data-ttu-id="1c20e-104">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1c20e-104">operator (C# Reference)</span></span>

<span data-ttu-id="1c20e-105">Il punto, `.`, viene usato generalmente per l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="1c20e-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="1c20e-106">Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c20e-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="1c20e-107">Usare `.` per accedere a uno spazio dei nomi annidato in uno spazio dei nomi, come illustra l'esempio seguente di [direttiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="1c20e-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="1c20e-108">Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1c20e-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="1c20e-109">Usare la [direttiva `using`](../keywords/using-directive.md) per rendere facoltativo l'uso di nomi qualificati.</span><span class="sxs-lookup"><span data-stu-id="1c20e-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="1c20e-110">Usare `.` per accedere ai [membri dei tipi](../../programming-guide/classes-and-structs/index.md#members), statici e non statici, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1c20e-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="1c20e-111">È anche possibile usare `.` per richiamare un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="1c20e-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1c20e-112">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="1c20e-112">Operator overloadability</span></span>

<span data-ttu-id="1c20e-113">Non è possibile sottoporre a overload l'operatore `.`.</span><span class="sxs-lookup"><span data-stu-id="1c20e-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1c20e-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1c20e-114">C# language specification</span></span>

<span data-ttu-id="1c20e-115">Per altre informazioni, vedere la sezione [Accesso ai membri](~/_csharplang/spec/expressions.md#member-access) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c20e-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c20e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c20e-116">See also</span></span>

- [<span data-ttu-id="1c20e-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1c20e-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1c20e-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1c20e-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1c20e-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1c20e-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="1c20e-120">[Operatori ?. e ?[]](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="1c20e-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>