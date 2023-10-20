
<script>
	// @ts-nocheck
	import toast, { Toaster } from 'svelte-french-toast';
	let step = 1;
	let firstName, lastName, email, gender, idNumber, phoneNumber, dob, password;

	const next = () => step++;
	const prev = () => step--;

	// Calculate progress
	let progress = 0;
	$: progress =
		(firstName ? 12.5 : 0) +
		(lastName ? 12.5 : 0) +
		(email ? 12.5 : 0) +
		(gender ? 12.5 : 0) +
		(idNumber ? 12.5 : 0) +
		(phoneNumber ? 12.5 : 0) +
		(dob ? 12.5 : 0) +
		(password ? 12.5 : 0);



		function success (){
	toast.success('yessss');
		}
	
	
</script>

<div class="flex m-4 h-full">
	<div class="w-1/2 h-auto bg-cover" style="background-image: url('/cars.jpg')" />

	<div class="w-1/2 border p-4 h-full">
		<div class="progress-bar bg-gray-400 relative">
			
			<div class="absolute top-0 left-0 w-full flex justify-between"><div
				class="progress h-1 bg-blue-500 transition-all duration-700 ease-in-out absolute "
				style="width: {progress}%"
			/>
				
			</div>
		</div>
		{#if step === 1}
			<div class="step mt-4">
				<h2 class="font-bold text-lg mb-4">Step 1</h2>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="firstName"
						>First Name</label
					>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="firstName"
						type="text"
						bind:value={firstName}
					/>
				</div>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="lastName">Last Name</label>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="lastName"
						type="text"
						bind:value={lastName}
					/>
				</div>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="email">Email</label>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="email"
						type="email"
						bind:value={email}
					/>
				</div>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="gender">Gender</label>
					<select
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="gender"
						bind:value={gender}
					>
					<option ></option>
						<option>Male</option>
						<option>Female</option>
						<option>Other</option>
					</select>
				</div>
				<button
					class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
					on:click={success}>Next</button
				>
			</div>
		{/if}

		{#if step === 2}
			<div class="step mt-4">
				<h2 class="font-bold text-lg mb-4">Step 2</h2>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="idNumber">ID Number</label>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="idNumber"
						type="number"
						bind:value={idNumber}
					/>
				</div>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="phoneNumber"
						>Phone Number</label
					>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="phoneNumber"
						type="tel"
						bind:value={phoneNumber}
					/>
				</div>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="dob">Date of Birth</label>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="dob"
						type="date"
						bind:value={dob}
					/>
				</div>
				<div class="mb-4">
					<label class="block text-gray-700 text-sm font-bold mb-2" for="password">Password</label>
					<input
						class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight"
						id="password"
						type="password"
						bind:value={password}
					/>
				</div>
				<button
					class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
					on:click={prev}>Previous</button
				>
				<button
					class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
					on:click={next}>Next</button
				>
			</div>
		{/if}
		{#if step === 3}
			<div class="mt-4">
				<button
					class="pt-3 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
					on:click={prev}>Previous</button
				>
			</div>
		{/if}
	</div>
</div>
<Toaster />