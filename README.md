// Example Minecraft Shader

#version 330 core

// Input from Minecraft
in vec2 TexCoords;
in vec3 FragPos;
in vec3 Normal;

// Output color
out vec4 FragColor;

// Uniforms for customization
uniform float time;  // Elapsed time
uniform sampler2D ourTexture;  // Texture sampler

void main()
{
    // Perform shader calculations here

    // Example: Apply texture
    vec3 textureColor = texture(ourTexture, TexCoords).rgb;

    // Example: Add time-based animation
    vec3 animatedColor = textureColor * abs(sin(time));

    // Example: Apply lighting using the normal vector
    float ambientStrength = 0.1;
    vec3 ambient = ambientStrength * textureColor;

    vec3 result = ambient + animatedColor;

    // Output final color
    FragColor = vec4(result, 1.0);
}
