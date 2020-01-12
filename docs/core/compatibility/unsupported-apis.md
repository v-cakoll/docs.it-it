---
title: API non supportate in .NET Core
description: Informazioni sulle API del .NET Framework che generano sempre un'eccezione in .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901495"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="c7eca-103">API che generano sempre eccezioni in .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7eca-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="c7eca-104">Le API seguenti eseguiranno sempre un <xref:System.PlatformNotSupportedException> quando vengono eseguite in .NET Core sulla piattaforma specificata.</span><span class="sxs-lookup"><span data-stu-id="c7eca-104">The following APIs will always through a <xref:System.PlatformNotSupportedException> when run on .NET Core on the specified platform.</span></span>

<span data-ttu-id="c7eca-105">Questo articolo organizza i membri API interessati in base allo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c7eca-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c7eca-106">Questo articolo è un lavoro in corso.</span><span class="sxs-lookup"><span data-stu-id="c7eca-106">This article is a work-in-progress.</span></span> <span data-ttu-id="c7eca-107">Non si tratta di un elenco completo di API che generano eccezioni in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7eca-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="c7eca-108">Questo articolo non include le implementazioni esplicite dell'interfaccia per la serializzazione binaria generata in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7eca-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="c7eca-109">Per altre informazioni, vedere [serializzazione binaria in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="c7eca-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="c7eca-110">System</span><span class="sxs-lookup"><span data-stu-id="c7eca-110">System</span></span>

| <span data-ttu-id="c7eca-111">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-111">Member</span></span> | <span data-ttu-id="c7eca-112">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-112">Platform</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-113">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-114">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="c7eca-115">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="c7eca-116">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-117">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="c7eca-118">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c7eca-119">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c7eca-120">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-121">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-122">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="c7eca-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="c7eca-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="c7eca-124">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-124">Member</span></span> | <span data-ttu-id="c7eca-125">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-125">Platform</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-126">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-127">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-128">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="c7eca-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="c7eca-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="c7eca-130">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-130">Member</span></span> | <span data-ttu-id="c7eca-131">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-131">Platform</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-132">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-133">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-134">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="c7eca-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="c7eca-135">System.Configuration</span></span>

| <span data-ttu-id="c7eca-136">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-136">Member</span></span> | <span data-ttu-id="c7eca-137">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-137">Platform</span></span> |
| - | - |
| <span data-ttu-id="c7eca-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="c7eca-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="c7eca-139">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="c7eca-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="c7eca-140">System.Console</span></span>

| <span data-ttu-id="c7eca-141">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-141">Member</span></span> | <span data-ttu-id="c7eca-142">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-142">Platform</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="c7eca-143">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-143">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-145">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-145">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-147">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-147">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-149">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-149">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="c7eca-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c7eca-151">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-152">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-153">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-154">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-154">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="c7eca-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c7eca-156">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-156">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-158">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-158">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-160">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-160">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-162">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-162">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-164">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="c7eca-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="c7eca-165">System.Data.Common</span></span>

| <span data-ttu-id="c7eca-166">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-166">Member</span></span> | <span data-ttu-id="c7eca-167">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-167">Platform</span></span> |
| - | - |
| <span data-ttu-id="c7eca-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="c7eca-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="c7eca-169">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="c7eca-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="c7eca-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="c7eca-171">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-171">Member</span></span> | <span data-ttu-id="c7eca-172">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-172">Platform</span></span> |
| - | - |
| <span data-ttu-id="c7eca-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-174">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eca-174">Linux</span></span> |
| <span data-ttu-id="c7eca-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-176">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eca-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="c7eca-177">macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="c7eca-178">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-179">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="c7eca-180">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="c7eca-181">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="c7eca-182">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="c7eca-183">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-183">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-185">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-185">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="c7eca-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c7eca-187">macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-187">macOS</span></span> |
| <span data-ttu-id="c7eca-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-189">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="c7eca-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="c7eca-190">System.IO</span></span>

| <span data-ttu-id="c7eca-191">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-191">Member</span></span> | <span data-ttu-id="c7eca-192">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-192">Platform</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-193">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-194">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="c7eca-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="c7eca-195">System.IO.Pipes</span></span>

| <span data-ttu-id="c7eca-196">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-196">Member</span></span> | <span data-ttu-id="c7eca-197">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-197">Platform</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="c7eca-198">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="c7eca-199">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c7eca-200">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c7eca-201">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-201">Linux and macOS</span></span> |
| <span data-ttu-id="c7eca-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-203">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="c7eca-204">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="c7eca-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="c7eca-205">System.Media</span></span>

| <span data-ttu-id="c7eca-206">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-206">Member</span></span> | <span data-ttu-id="c7eca-207">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-207">Platform</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-208">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="c7eca-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="c7eca-209">System.Net</span></span>

| <span data-ttu-id="c7eca-210">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-210">Member</span></span> | <span data-ttu-id="c7eca-211">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-211">Platform</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-212">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-213">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-214">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-215">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-216">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-217">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-218">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-219">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-220">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-221">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-222">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="c7eca-223">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-224">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-225">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-226">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-227">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-228">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="c7eca-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="c7eca-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="c7eca-230">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-230">Member</span></span> | <span data-ttu-id="c7eca-231">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-231">Platform</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="c7eca-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="c7eca-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="c7eca-233">System.Net.Sockets</span></span>

| <span data-ttu-id="c7eca-234">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-234">Member</span></span> | <span data-ttu-id="c7eca-235">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-235">Platform</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-236">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="c7eca-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="c7eca-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="c7eca-238">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-238">Member</span></span> | <span data-ttu-id="c7eca-239">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-239">Platform</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="c7eca-240">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="c7eca-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="c7eca-241">System.Reflection</span></span>

| <span data-ttu-id="c7eca-242">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-242">Member</span></span> | <span data-ttu-id="c7eca-243">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-243">Platform</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-244">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-245">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-246">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-247">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-248">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-249">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="c7eca-250">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="c7eca-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="c7eca-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="c7eca-252">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-252">Member</span></span> | <span data-ttu-id="c7eca-253">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-253">Platform</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="c7eca-254">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="c7eca-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="c7eca-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="c7eca-256">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-256">Member</span></span> | <span data-ttu-id="c7eca-257">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-257">Platform</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-258">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="c7eca-259">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-260">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-261">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-262">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-263">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-264">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="c7eca-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="c7eca-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="c7eca-266">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-266">Member</span></span> | <span data-ttu-id="c7eca-267">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-267">Platform</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="c7eca-268">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="c7eca-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="c7eca-269">System.Security</span></span>

| <span data-ttu-id="c7eca-270">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-270">Member</span></span> | <span data-ttu-id="c7eca-271">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-271">Platform</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="c7eca-272">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c7eca-273">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-274">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="c7eca-275">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c7eca-276">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="c7eca-277">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="c7eca-278">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="c7eca-279">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c7eca-280">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c7eca-281">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="c7eca-282">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-283">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="c7eca-284">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="c7eca-285">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="c7eca-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="c7eca-286">System.Security.Claims</span></span>

| <span data-ttu-id="c7eca-287">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-287">Member</span></span> | <span data-ttu-id="c7eca-288">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-288">Platform</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="c7eca-289">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-290">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-291">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-292">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-293">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="c7eca-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="c7eca-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="c7eca-295">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-295">Member</span></span> | <span data-ttu-id="c7eca-296">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-296">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-297">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-298">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="c7eca-299">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="c7eca-300">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="c7eca-301">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c7eca-302">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="c7eca-303">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="c7eca-304">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="c7eca-305">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="c7eca-306">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="c7eca-307">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="c7eca-308">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="c7eca-309">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c7eca-310">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c7eca-311">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-312">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="c7eca-313">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-314">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-315">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-316">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-317">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c7eca-318">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-319">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-320">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-321">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="c7eca-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-322">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-323">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c7eca-324">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-325">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="c7eca-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="c7eca-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="c7eca-327">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-327">Member</span></span> | <span data-ttu-id="c7eca-328">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-328">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-329">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-330">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="c7eca-331">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="c7eca-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="c7eca-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="c7eca-333">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-333">Member</span></span> | <span data-ttu-id="c7eca-334">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-334">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-335">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-336">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-337">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-337">All</span></span> |
| <span data-ttu-id="c7eca-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="c7eca-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7eca-339">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="c7eca-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="c7eca-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="c7eca-341">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-341">Member</span></span> | <span data-ttu-id="c7eca-342">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-342">Platform</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-343">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="c7eca-344">System. Security. Policy</span><span class="sxs-lookup"><span data-stu-id="c7eca-344">System.Security.Policy</span></span>

| <span data-ttu-id="c7eca-345">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-345">Member</span></span> | <span data-ttu-id="c7eca-346">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-346">Platform</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-347">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="c7eca-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="c7eca-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="c7eca-349">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-349">Member</span></span> | <span data-ttu-id="c7eca-350">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-350">Platform</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-351">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="c7eca-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="c7eca-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="c7eca-353">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-353">Member</span></span> | <span data-ttu-id="c7eca-354">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-354">Platform</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-355">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="c7eca-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="c7eca-356">System.Threading</span></span>

| <span data-ttu-id="c7eca-357">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-357">Member</span></span> | <span data-ttu-id="c7eca-358">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-358">Platform</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-359">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-360">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="c7eca-361">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="c7eca-362">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="c7eca-363">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="c7eca-364">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="c7eca-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="c7eca-365">System.Xml</span></span>

| <span data-ttu-id="c7eca-366">Member</span><span class="sxs-lookup"><span data-stu-id="c7eca-366">Member</span></span> | <span data-ttu-id="c7eca-367">Platform</span><span class="sxs-lookup"><span data-stu-id="c7eca-367">Platform</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-368">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-369">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c7eca-370">Tutte le</span><span class="sxs-lookup"><span data-stu-id="c7eca-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="c7eca-371">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7eca-371">See also</span></span>

- [<span data-ttu-id="c7eca-372">Modifiche di rilievo per la migrazione da .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7eca-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="c7eca-373">Serializzazione binaria in .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7eca-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="c7eca-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="c7eca-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
