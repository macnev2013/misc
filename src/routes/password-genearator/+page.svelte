<script>
    import Input from "$lib/Input.svelte";
    import Card from '$lib/Card.svelte';
    import Checkbox from "$lib/Checkbox.svelte";
    import Slider from "$lib/Slider.svelte";
    import Button from "$lib/Button.svelte";

    let password = '';
    generatePassword(32, true, true, false);

    /**
     * @param {number} length
     * @param {boolean} useUppercase
     * @param {boolean} useNumbers
     * @param {boolean} useSpecialChars
     */
    function generatePassword(length, useUppercase, useNumbers, useSpecialChars) {
        password = '';
        const lowerCaseChars = 'abcdefghijklmnopqrstuvwxyz';
        const upperCaseChars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
        const numberChars = '0123456789';
        const specialChars = '!@#$%^&*()-=_+[]{}|;:,.<>?';

        let allChars = lowerCaseChars;
        if (useUppercase) {
            allChars += upperCaseChars;
        }
        if (useNumbers) {
            allChars += numberChars;
        }
        if (useSpecialChars) {
            allChars += specialChars;
        }

        for (let i = 0; i < length; i++) {
            const randomIndex = Math.floor(Math.random() * allChars.length);
            password += allChars[randomIndex];
        }
    }
</script>

<main>
    <div class="app-content">
        <h1 class="app-title">Password Generator</h1>
        <Input disabled value={password} placeholder="Password will be generated">
            <Button on:click={() => navigator.clipboard.writeText(password)}>
                <i class="mi mi-clipboard"><span class="u-sr-only"></span></i>
            </Button>

        </Input>

        <span class="spacer"></span>
        <Card>
            <Checkbox id="useLowerCase" name="Use Lower Case" value="useLowerCase"/>
            <Checkbox id="useUpperCase" name="Use Upper Case" value="useUpperCase"/>
            <Checkbox id="useNumbers" name="Use Numbers" value="useNumbers"/>
            <Checkbox id="useSpecialChars" name="Use Special Characters" value="useSpecialChars"/>
            <Slider id="length" title="Password Length"/>
        </Card>
        <span class="spacer"></span>
        <Button on:click={() => generatePassword(
            document.getElementById('length').value,
            document.getElementById('useUpperCase').checked,
            document.getElementById('useNumbers').checked,
            document.getElementById('useSpecialChars').checked)}>
            Generate</Button>
    </div>
</main>

<style>
    .app-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 100vh;
    }

    .app-title {
        text-align: center;
        font-size: 3rem;
        margin-bottom: 3rem;
    }

    .spacer {
        margin: 1rem;
    }

</style>
