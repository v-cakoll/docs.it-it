---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365906"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="db9d0-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="db9d0-102">ODBC Schema Collections</span></span>

<span data-ttu-id="db9d0-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="db9d0-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="db9d0-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="db9d0-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="db9d0-105">Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="db9d0-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="db9d0-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="db9d0-106">Tables</span></span>

- <span data-ttu-id="db9d0-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="db9d0-107">Indexes</span></span>

- <span data-ttu-id="db9d0-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="db9d0-108">Columns</span></span>

- <span data-ttu-id="db9d0-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="db9d0-109">Procedures</span></span>

- <span data-ttu-id="db9d0-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="db9d0-110">ProcedureColumns</span></span>

- <span data-ttu-id="db9d0-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="db9d0-111">ProcedureParameters</span></span>

- <span data-ttu-id="db9d0-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="db9d0-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="db9d0-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="db9d0-113">Tables and Views</span></span>

|<span data-ttu-id="db9d0-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-114">ColumnName</span></span>|<span data-ttu-id="db9d0-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-116">TABLE_CAT</span></span>|<span data-ttu-id="db9d0-117">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-117">String</span></span>|
|<span data-ttu-id="db9d0-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-118">TABLE_SCHEM</span></span>|<span data-ttu-id="db9d0-119">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-119">String</span></span>|
|<span data-ttu-id="db9d0-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-120">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-121">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-121">String</span></span>|
|<span data-ttu-id="db9d0-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-122">TABLE_TYPE</span></span>|<span data-ttu-id="db9d0-123">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-123">String</span></span>|
|<span data-ttu-id="db9d0-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-124">REMARKS</span></span>|<span data-ttu-id="db9d0-125">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="db9d0-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="db9d0-126">Indexes</span></span>

|<span data-ttu-id="db9d0-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-127">ColumnName</span></span>|<span data-ttu-id="db9d0-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-129">TABLE_CAT</span></span>|<span data-ttu-id="db9d0-130">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-130">String</span></span>|
|<span data-ttu-id="db9d0-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-131">TABLE_SCHEM</span></span>|<span data-ttu-id="db9d0-132">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-132">String</span></span>|
|<span data-ttu-id="db9d0-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-133">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-134">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-134">String</span></span>|
|<span data-ttu-id="db9d0-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="db9d0-135">NON_UNIQUE</span></span>|<span data-ttu-id="db9d0-136">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-136">Int16</span></span>|
|<span data-ttu-id="db9d0-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="db9d0-138">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-138">String</span></span>|
|<span data-ttu-id="db9d0-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-139">INDEX_NAME</span></span>|<span data-ttu-id="db9d0-140">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-140">String</span></span>|
|<span data-ttu-id="db9d0-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-141">TYPE</span></span>|<span data-ttu-id="db9d0-142">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-142">Int16</span></span>|
|<span data-ttu-id="db9d0-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-144">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-144">Int16</span></span>|
|<span data-ttu-id="db9d0-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-145">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-146">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-146">String</span></span>|
|<span data-ttu-id="db9d0-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="db9d0-147">ASC_OR_DESC</span></span>|<span data-ttu-id="db9d0-148">Stringa</span><span class="sxs-lookup"><span data-stu-id="db9d0-148">String</span></span>|
|<span data-ttu-id="db9d0-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="db9d0-149">CARDINALITY</span></span>|<span data-ttu-id="db9d0-150">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-150">Int32</span></span>|
|<span data-ttu-id="db9d0-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="db9d0-151">PAGES</span></span>|<span data-ttu-id="db9d0-152">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-152">Int32</span></span>|
|<span data-ttu-id="db9d0-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-153">FILTER_CONDITION</span></span>|<span data-ttu-id="db9d0-154">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-154">String</span></span>|
|<span data-ttu-id="db9d0-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="db9d0-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="db9d0-156">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-156">String</span></span>|
|<span data-ttu-id="db9d0-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-158">Byte</span><span class="sxs-lookup"><span data-stu-id="db9d0-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="db9d0-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="db9d0-159">Columns</span></span>

|<span data-ttu-id="db9d0-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-160">ColumnName</span></span>|<span data-ttu-id="db9d0-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-162">TABLE_CAT</span></span>|<span data-ttu-id="db9d0-163">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-163">String</span></span>|
|<span data-ttu-id="db9d0-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-164">TABLE_SCHEM</span></span>|<span data-ttu-id="db9d0-165">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-165">String</span></span>|
|<span data-ttu-id="db9d0-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-166">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-167">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-167">String</span></span>|
|<span data-ttu-id="db9d0-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-168">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-169">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-169">String</span></span>|
|<span data-ttu-id="db9d0-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-170">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-171">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-171">Int16</span></span>|
|<span data-ttu-id="db9d0-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-172">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-173">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-173">String</span></span>|
|<span data-ttu-id="db9d0-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="db9d0-174">COLUMN_SIZE</span></span>|<span data-ttu-id="db9d0-175">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-175">Int32</span></span>|
|<span data-ttu-id="db9d0-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="db9d0-177">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-177">Int32</span></span>|
|<span data-ttu-id="db9d0-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="db9d0-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="db9d0-179">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-179">Int16</span></span>|
|<span data-ttu-id="db9d0-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="db9d0-181">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-181">Int16</span></span>|
|<span data-ttu-id="db9d0-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-182">NULLABLE</span></span>|<span data-ttu-id="db9d0-183">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-183">Int16</span></span>|
|<span data-ttu-id="db9d0-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-184">REMARKS</span></span>|<span data-ttu-id="db9d0-185">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-185">String</span></span>|
|<span data-ttu-id="db9d0-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="db9d0-186">COLUMN_DEF</span></span>|<span data-ttu-id="db9d0-187">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-187">String</span></span>|
|<span data-ttu-id="db9d0-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-189">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-189">Int16</span></span>|
|<span data-ttu-id="db9d0-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="db9d0-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="db9d0-191">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-191">Int16</span></span>|
|<span data-ttu-id="db9d0-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="db9d0-193">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-193">Int32</span></span>|
|<span data-ttu-id="db9d0-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-195">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-195">Int32</span></span>|
|<span data-ttu-id="db9d0-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-196">IS_NULLABLE</span></span>|<span data-ttu-id="db9d0-197">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-197">String</span></span>|
|<span data-ttu-id="db9d0-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="db9d0-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="db9d0-199">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-199">String</span></span>|
|<span data-ttu-id="db9d0-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="db9d0-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="db9d0-201">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-201">String</span></span>|
|<span data-ttu-id="db9d0-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-203">Byte</span><span class="sxs-lookup"><span data-stu-id="db9d0-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="db9d0-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="db9d0-204">Procedures</span></span>

|<span data-ttu-id="db9d0-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-205">ColumnName</span></span>|<span data-ttu-id="db9d0-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="db9d0-208">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-208">String</span></span>|
|<span data-ttu-id="db9d0-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="db9d0-210">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-210">String</span></span>|
|<span data-ttu-id="db9d0-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-212">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-212">String</span></span>|
|<span data-ttu-id="db9d0-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="db9d0-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="db9d0-214">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-214">Int32</span></span>|
|<span data-ttu-id="db9d0-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="db9d0-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="db9d0-216">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-216">Int32</span></span>|
|<span data-ttu-id="db9d0-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="db9d0-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="db9d0-218">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-218">Int32</span></span>|
|<span data-ttu-id="db9d0-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-219">REMARKS</span></span>|<span data-ttu-id="db9d0-220">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-220">String</span></span>|
|<span data-ttu-id="db9d0-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="db9d0-222">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="db9d0-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="db9d0-223">ProcedureColumns</span></span>

|<span data-ttu-id="db9d0-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-224">ColumnName</span></span>|<span data-ttu-id="db9d0-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="db9d0-227">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-227">String</span></span>|
|<span data-ttu-id="db9d0-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="db9d0-229">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-229">String</span></span>|
|<span data-ttu-id="db9d0-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-231">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-231">String</span></span>|
|<span data-ttu-id="db9d0-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-232">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-233">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-233">String</span></span>|
|<span data-ttu-id="db9d0-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-234">COLUMN_TYPE</span></span>|<span data-ttu-id="db9d0-235">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-235">Int16</span></span>|
|<span data-ttu-id="db9d0-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-236">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-237">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-237">Int16</span></span>|
|<span data-ttu-id="db9d0-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-238">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-239">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-239">String</span></span>|
|<span data-ttu-id="db9d0-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="db9d0-240">COLUMN_SIZE</span></span>|<span data-ttu-id="db9d0-241">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-241">Int32</span></span>|
|<span data-ttu-id="db9d0-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="db9d0-243">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-243">Int32</span></span>|
|<span data-ttu-id="db9d0-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="db9d0-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="db9d0-245">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-245">Int16</span></span>|
|<span data-ttu-id="db9d0-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="db9d0-247">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-247">Int16</span></span>|
|<span data-ttu-id="db9d0-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-248">NULLABLE</span></span>|<span data-ttu-id="db9d0-249">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-249">Int16</span></span>|
|<span data-ttu-id="db9d0-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-250">REMARKS</span></span>|<span data-ttu-id="db9d0-251">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-251">String</span></span>|
|<span data-ttu-id="db9d0-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="db9d0-252">COLUMN_DEF</span></span>|<span data-ttu-id="db9d0-253">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-253">String</span></span>|
|<span data-ttu-id="db9d0-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-255">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-255">Int16</span></span>|
|<span data-ttu-id="db9d0-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="db9d0-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="db9d0-257">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-257">Int16</span></span>|
|<span data-ttu-id="db9d0-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="db9d0-259">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-259">Int32</span></span>|
|<span data-ttu-id="db9d0-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-261">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-261">Int32</span></span>|
|<span data-ttu-id="db9d0-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-262">IS_NULLABLE</span></span>|<span data-ttu-id="db9d0-263">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-263">String</span></span>|
|<span data-ttu-id="db9d0-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="db9d0-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="db9d0-265">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-265">String</span></span>|
|<span data-ttu-id="db9d0-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="db9d0-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="db9d0-267">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-267">String</span></span>|
|<span data-ttu-id="db9d0-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-269">Byte</span><span class="sxs-lookup"><span data-stu-id="db9d0-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="db9d0-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="db9d0-270">ProcedureParameters</span></span>

|<span data-ttu-id="db9d0-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-271">ColumnName</span></span>|<span data-ttu-id="db9d0-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="db9d0-274">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-274">String</span></span>|
|<span data-ttu-id="db9d0-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="db9d0-276">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-276">String</span></span>|
|<span data-ttu-id="db9d0-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-278">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-278">String</span></span>|
|<span data-ttu-id="db9d0-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-279">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-280">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-280">String</span></span>|
|<span data-ttu-id="db9d0-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-281">COLUMN_TYPE</span></span>|<span data-ttu-id="db9d0-282">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-282">Int16</span></span>|
|<span data-ttu-id="db9d0-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-283">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-284">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-284">Int16</span></span>|
|<span data-ttu-id="db9d0-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-285">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-286">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-286">String</span></span>|
|<span data-ttu-id="db9d0-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="db9d0-287">COLUMN_SIZE</span></span>|<span data-ttu-id="db9d0-288">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-288">Int32</span></span>|
|<span data-ttu-id="db9d0-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="db9d0-290">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-290">Int32</span></span>|
|<span data-ttu-id="db9d0-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="db9d0-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="db9d0-292">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-292">Int16</span></span>|
|<span data-ttu-id="db9d0-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="db9d0-294">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-294">Int16</span></span>|
|<span data-ttu-id="db9d0-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-295">NULLABLE</span></span>|<span data-ttu-id="db9d0-296">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-296">Int16</span></span>|
|<span data-ttu-id="db9d0-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-297">REMARKS</span></span>|<span data-ttu-id="db9d0-298">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-298">String</span></span>|
|<span data-ttu-id="db9d0-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="db9d0-299">COLUMN_DEF</span></span>|<span data-ttu-id="db9d0-300">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-300">String</span></span>|
|<span data-ttu-id="db9d0-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-302">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-302">Int16</span></span>|
|<span data-ttu-id="db9d0-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="db9d0-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="db9d0-304">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-304">Int16</span></span>|
|<span data-ttu-id="db9d0-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="db9d0-306">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-306">Int32</span></span>|
|<span data-ttu-id="db9d0-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-308">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-308">Int32</span></span>|
|<span data-ttu-id="db9d0-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-309">IS_NULLABLE</span></span>|<span data-ttu-id="db9d0-310">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-310">String</span></span>|
|<span data-ttu-id="db9d0-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="db9d0-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="db9d0-312">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-312">String</span></span>|
|<span data-ttu-id="db9d0-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="db9d0-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="db9d0-314">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-314">String</span></span>|
|<span data-ttu-id="db9d0-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-316">Byte</span><span class="sxs-lookup"><span data-stu-id="db9d0-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="db9d0-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="db9d0-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="db9d0-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="db9d0-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="db9d0-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="db9d0-319">Tables</span></span>

- <span data-ttu-id="db9d0-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="db9d0-320">Columns</span></span>

- <span data-ttu-id="db9d0-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="db9d0-321">Procedures</span></span>

- <span data-ttu-id="db9d0-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="db9d0-322">ProcedureColumns</span></span>

- <span data-ttu-id="db9d0-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="db9d0-323">ProcedureParameters</span></span>

- <span data-ttu-id="db9d0-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="db9d0-324">Views</span></span>

- <span data-ttu-id="db9d0-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="db9d0-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="db9d0-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="db9d0-326">Tables and Views</span></span>

|<span data-ttu-id="db9d0-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-327">ColumnName</span></span>|<span data-ttu-id="db9d0-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-330">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-330">String</span></span>|
|<span data-ttu-id="db9d0-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-331">TABLE_OWNER</span></span>|<span data-ttu-id="db9d0-332">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-332">String</span></span>|
|<span data-ttu-id="db9d0-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-333">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-334">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-334">String</span></span>|
|<span data-ttu-id="db9d0-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-335">TABLE_TYPE</span></span>|<span data-ttu-id="db9d0-336">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-336">String</span></span>|
|<span data-ttu-id="db9d0-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-337">REMARKS</span></span>|<span data-ttu-id="db9d0-338">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="db9d0-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="db9d0-339">Columns</span></span>

|<span data-ttu-id="db9d0-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-340">ColumnName</span></span>|<span data-ttu-id="db9d0-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-343">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-343">String</span></span>|
|<span data-ttu-id="db9d0-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-344">TABLE_OWNER</span></span>|<span data-ttu-id="db9d0-345">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-345">String</span></span>|
|<span data-ttu-id="db9d0-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-346">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-347">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-347">String</span></span>|
|<span data-ttu-id="db9d0-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-348">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-349">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-349">String</span></span>|
|<span data-ttu-id="db9d0-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-350">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-351">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-351">Int16</span></span>|
|<span data-ttu-id="db9d0-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-352">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-353">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-353">String</span></span>|
|<span data-ttu-id="db9d0-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="db9d0-354">PRECISION</span></span>|<span data-ttu-id="db9d0-355">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-355">Int32</span></span>|
|<span data-ttu-id="db9d0-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-356">LENGTH</span></span>|<span data-ttu-id="db9d0-357">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-357">Int32</span></span>|
|<span data-ttu-id="db9d0-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="db9d0-358">SCALE</span></span>|<span data-ttu-id="db9d0-359">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-359">Int16</span></span>|
|<span data-ttu-id="db9d0-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-360">RADIX</span></span>|<span data-ttu-id="db9d0-361">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-361">Int16</span></span>|
|<span data-ttu-id="db9d0-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-362">NULLABLE</span></span>|<span data-ttu-id="db9d0-363">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-363">Int16</span></span>|
|<span data-ttu-id="db9d0-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-364">REMARKS</span></span>|<span data-ttu-id="db9d0-365">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-365">String</span></span>|
|<span data-ttu-id="db9d0-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-367">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="db9d0-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="db9d0-368">Procedures</span></span>

|<span data-ttu-id="db9d0-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-369">ColumnName</span></span>|<span data-ttu-id="db9d0-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-372">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-372">String</span></span>|
|<span data-ttu-id="db9d0-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="db9d0-374">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-374">String</span></span>|
|<span data-ttu-id="db9d0-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-376">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-376">String</span></span>|
|<span data-ttu-id="db9d0-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="db9d0-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="db9d0-378">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-378">Int16</span></span>|
|<span data-ttu-id="db9d0-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="db9d0-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="db9d0-380">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-380">Int16</span></span>|
|<span data-ttu-id="db9d0-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="db9d0-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="db9d0-382">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-382">Int16</span></span>|
|<span data-ttu-id="db9d0-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-383">REMARKS</span></span>|<span data-ttu-id="db9d0-384">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-384">String</span></span>|
|<span data-ttu-id="db9d0-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="db9d0-386">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="db9d0-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="db9d0-387">ProcedureColumns</span></span>

|<span data-ttu-id="db9d0-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-388">ColumnName</span></span>|<span data-ttu-id="db9d0-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-391">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-391">String</span></span>|
|<span data-ttu-id="db9d0-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="db9d0-393">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-393">String</span></span>|
|<span data-ttu-id="db9d0-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-395">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-395">String</span></span>|
|<span data-ttu-id="db9d0-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-396">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-397">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-397">String</span></span>|
|<span data-ttu-id="db9d0-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-398">COLUMN_TYPE</span></span>|<span data-ttu-id="db9d0-399">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-399">Int16</span></span>|
|<span data-ttu-id="db9d0-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-400">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-401">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-401">Int16</span></span>|
|<span data-ttu-id="db9d0-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-402">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-403">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-403">String</span></span>|
|<span data-ttu-id="db9d0-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="db9d0-404">PRECISION</span></span>|<span data-ttu-id="db9d0-405">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-405">Int32</span></span>|
|<span data-ttu-id="db9d0-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-406">LENGTH</span></span>|<span data-ttu-id="db9d0-407">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-407">Int32</span></span>|
|<span data-ttu-id="db9d0-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="db9d0-408">SCALE</span></span>|<span data-ttu-id="db9d0-409">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-409">Int16</span></span>|
|<span data-ttu-id="db9d0-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-410">RADIX</span></span>|<span data-ttu-id="db9d0-411">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-411">Int16</span></span>|
|<span data-ttu-id="db9d0-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-412">NULLABLE</span></span>|<span data-ttu-id="db9d0-413">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-413">Int16</span></span>|
|<span data-ttu-id="db9d0-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-414">REMARKS</span></span>|<span data-ttu-id="db9d0-415">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-415">String</span></span>|
|<span data-ttu-id="db9d0-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="db9d0-416">OVERLOAD</span></span>|<span data-ttu-id="db9d0-417">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-417">Int32</span></span>|
|<span data-ttu-id="db9d0-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-419">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="db9d0-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="db9d0-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="db9d0-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="db9d0-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="db9d0-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="db9d0-422">Tables</span></span>

- <span data-ttu-id="db9d0-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="db9d0-423">Indexes</span></span>

- <span data-ttu-id="db9d0-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="db9d0-424">Columns</span></span>

- <span data-ttu-id="db9d0-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="db9d0-425">Procedures</span></span>

- <span data-ttu-id="db9d0-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="db9d0-426">ProcedureColumns</span></span>

- <span data-ttu-id="db9d0-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="db9d0-427">ProcedureParameters</span></span>

- <span data-ttu-id="db9d0-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="db9d0-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="db9d0-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="db9d0-429">Tables and Views</span></span>

|<span data-ttu-id="db9d0-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-430">ColumnName</span></span>|<span data-ttu-id="db9d0-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-433">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-433">String</span></span>|
|<span data-ttu-id="db9d0-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-434">TABLE_OWNER</span></span>|<span data-ttu-id="db9d0-435">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-435">String</span></span>|
|<span data-ttu-id="db9d0-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-436">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-437">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-437">String</span></span>|
|<span data-ttu-id="db9d0-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-438">TABLE_TYPE</span></span>|<span data-ttu-id="db9d0-439">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-439">String</span></span>|
|<span data-ttu-id="db9d0-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-440">REMARKS</span></span>|<span data-ttu-id="db9d0-441">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="db9d0-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="db9d0-442">Columns</span></span>

|<span data-ttu-id="db9d0-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-443">ColumnName</span></span>|<span data-ttu-id="db9d0-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-446">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-446">String</span></span>|
|<span data-ttu-id="db9d0-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-447">TABLE_OWNER</span></span>|<span data-ttu-id="db9d0-448">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-448">String</span></span>|
|<span data-ttu-id="db9d0-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-449">TABLE_NAME</span></span>|<span data-ttu-id="db9d0-450">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-450">String</span></span>|
|<span data-ttu-id="db9d0-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-451">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-452">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-452">String</span></span>|
|<span data-ttu-id="db9d0-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-453">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-454">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-454">Int16</span></span>|
|<span data-ttu-id="db9d0-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-455">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-456">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-456">String</span></span>|
|<span data-ttu-id="db9d0-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="db9d0-457">PRECISION</span></span>|<span data-ttu-id="db9d0-458">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-458">Int32</span></span>|
|<span data-ttu-id="db9d0-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-459">LENGTH</span></span>|<span data-ttu-id="db9d0-460">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-460">Int32</span></span>|
|<span data-ttu-id="db9d0-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="db9d0-461">SCALE</span></span>|<span data-ttu-id="db9d0-462">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-462">Int16</span></span>|
|<span data-ttu-id="db9d0-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-463">RADIX</span></span>|<span data-ttu-id="db9d0-464">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-464">Int16</span></span>|
|<span data-ttu-id="db9d0-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-465">NULLABLE</span></span>|<span data-ttu-id="db9d0-466">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-466">Int16</span></span>|
|<span data-ttu-id="db9d0-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-467">REMARKS</span></span>|<span data-ttu-id="db9d0-468">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-468">String</span></span>|
|<span data-ttu-id="db9d0-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-470">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="db9d0-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="db9d0-471">Procedures</span></span>

|<span data-ttu-id="db9d0-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-472">ColumnName</span></span>|<span data-ttu-id="db9d0-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-475">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-475">String</span></span>|
|<span data-ttu-id="db9d0-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="db9d0-477">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-477">String</span></span>|
|<span data-ttu-id="db9d0-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-479">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-479">String</span></span>|
|<span data-ttu-id="db9d0-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="db9d0-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="db9d0-481">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-481">Int16</span></span>|
|<span data-ttu-id="db9d0-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="db9d0-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="db9d0-483">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-483">Int16</span></span>|
|<span data-ttu-id="db9d0-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="db9d0-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="db9d0-485">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-485">Int16</span></span>|
|<span data-ttu-id="db9d0-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-486">REMARKS</span></span>|<span data-ttu-id="db9d0-487">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-487">String</span></span>|
|<span data-ttu-id="db9d0-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="db9d0-489">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="db9d0-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="db9d0-490">ProcedureColumns</span></span>

|<span data-ttu-id="db9d0-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-491">ColumnName</span></span>|<span data-ttu-id="db9d0-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="db9d0-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="db9d0-494">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-494">String</span></span>|
|<span data-ttu-id="db9d0-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="db9d0-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="db9d0-496">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-496">String</span></span>|
|<span data-ttu-id="db9d0-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-498">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-498">String</span></span>|
|<span data-ttu-id="db9d0-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-499">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-500">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-500">String</span></span>|
|<span data-ttu-id="db9d0-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-501">COLUMN_TYPE</span></span>|<span data-ttu-id="db9d0-502">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-502">Int16</span></span>|
|<span data-ttu-id="db9d0-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-503">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-504">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-504">Int16</span></span>|
|<span data-ttu-id="db9d0-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-505">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-506">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-506">String</span></span>|
|<span data-ttu-id="db9d0-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="db9d0-507">PRECISION</span></span>|<span data-ttu-id="db9d0-508">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-508">Int32</span></span>|
|<span data-ttu-id="db9d0-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-509">LENGTH</span></span>|<span data-ttu-id="db9d0-510">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-510">Int32</span></span>|
|<span data-ttu-id="db9d0-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="db9d0-511">SCALE</span></span>|<span data-ttu-id="db9d0-512">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-512">Int16</span></span>|
|<span data-ttu-id="db9d0-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-513">RADIX</span></span>|<span data-ttu-id="db9d0-514">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-514">Int16</span></span>|
|<span data-ttu-id="db9d0-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-515">NULLABLE</span></span>|<span data-ttu-id="db9d0-516">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-516">Int16</span></span>|
|<span data-ttu-id="db9d0-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-517">REMARKS</span></span>|<span data-ttu-id="db9d0-518">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-518">String</span></span>|
|<span data-ttu-id="db9d0-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="db9d0-519">OVERLOAD</span></span>|<span data-ttu-id="db9d0-520">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-520">Int32</span></span>|
|<span data-ttu-id="db9d0-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-522">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="db9d0-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="db9d0-523">ProcedureParameters</span></span>

|<span data-ttu-id="db9d0-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="db9d0-524">ColumnName</span></span>|<span data-ttu-id="db9d0-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="db9d0-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="db9d0-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="db9d0-527">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-527">String</span></span>|
|<span data-ttu-id="db9d0-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="db9d0-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="db9d0-529">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-529">String</span></span>|
|<span data-ttu-id="db9d0-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="db9d0-531">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-531">String</span></span>|
|<span data-ttu-id="db9d0-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-532">COLUMN_NAME</span></span>|<span data-ttu-id="db9d0-533">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-533">String</span></span>|
|<span data-ttu-id="db9d0-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-534">COLUMN_TYPE</span></span>|<span data-ttu-id="db9d0-535">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-535">Int16</span></span>|
|<span data-ttu-id="db9d0-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-536">DATA_TYPE</span></span>|<span data-ttu-id="db9d0-537">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-537">Int16</span></span>|
|<span data-ttu-id="db9d0-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="db9d0-538">TYPE_NAME</span></span>|<span data-ttu-id="db9d0-539">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-539">String</span></span>|
|<span data-ttu-id="db9d0-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="db9d0-540">COLUMN_SIZE</span></span>|<span data-ttu-id="db9d0-541">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-541">Int32</span></span>|
|<span data-ttu-id="db9d0-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="db9d0-543">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-543">Int32</span></span>|
|<span data-ttu-id="db9d0-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="db9d0-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="db9d0-545">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-545">Int16</span></span>|
|<span data-ttu-id="db9d0-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="db9d0-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="db9d0-547">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-547">Int16</span></span>|
|<span data-ttu-id="db9d0-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-548">NULLABLE</span></span>|<span data-ttu-id="db9d0-549">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-549">Int16</span></span>|
|<span data-ttu-id="db9d0-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="db9d0-550">REMARKS</span></span>|<span data-ttu-id="db9d0-551">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-551">String</span></span>|
|<span data-ttu-id="db9d0-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="db9d0-552">COLUMN_DEF</span></span>|<span data-ttu-id="db9d0-553">String</span><span class="sxs-lookup"><span data-stu-id="db9d0-553">String</span></span>|
|<span data-ttu-id="db9d0-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="db9d0-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="db9d0-555">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-555">Int16</span></span>|
|<span data-ttu-id="db9d0-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="db9d0-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="db9d0-557">Int16</span><span class="sxs-lookup"><span data-stu-id="db9d0-557">Int16</span></span>|
|<span data-ttu-id="db9d0-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="db9d0-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="db9d0-559">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-559">Int32</span></span>|
|<span data-ttu-id="db9d0-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="db9d0-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="db9d0-561">Int32</span><span class="sxs-lookup"><span data-stu-id="db9d0-561">Int32</span></span>|
|<span data-ttu-id="db9d0-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="db9d0-562">IS_NULLABLE</span></span>|<span data-ttu-id="db9d0-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="db9d0-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="db9d0-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db9d0-564">See also</span></span>

- [<span data-ttu-id="db9d0-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="db9d0-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
