```php
<?php

namespace App\Developer;

#[AsHuman]
final class AlexDaubois extends AbstractSymfonyLeadDeveloper implements DeveloperInterface
{
    public const string FIRST_NAME = 'Alexandre';
    public const string LAST_NAME = 'Daubois';
    
    public function __construct(
        #[\SensitiveParameter] private \DateTimeImmutable $birthDate = new \DateTimeImmutable('1996-01-07T05:30:00+0200'),
        private string $currentCompany = 'Wanadev',
        private string $currentCity = 'Lyon, France'
    ) {
    }
    
    public function getBlog(): ?SocialAccountInterface
    {
        return new MediumPage('https://alex-daubois.medium.com/');
    }
    
    public function getX(): ?SocialAccountInterface
    {
        return new TwitterAccount('https://x.com/alexdaubois');
    }
    
    public function isCertified(): bool
    {
        return true;
    }
    
    public function getCertificationLabel(): ?string
    {
        return $this->isCertified() ? 'Symfony 6 Certified Developer (Expert)' : null;
    }
}
```
