import java.util.List;
import java.util.Arrays;
import java.util.Random;
import java.util.concurrent.Executors;
import java.util.concurrent.ScheduledExecutorService;
import java.util.concurrent.TimeUnit;

/**
 * BondageProjects Whisperer
 * 
 * Sends random whispers to the player periodically.
 */
public class BondageProjectsWhisperer {

    private static final List<String> WHISPERS = Arrays.asList(
        "Just breathe, baby... no need to think right now.",
        "Let the thoughts float away... you don’t need them.",
        "Every word I say makes you feel prettier.",
        // ... (all other whispers here, truncated for brevity)
        "Say “yes” and smile. That’s all you need now."
    );

    private final Random random = new Random();
    private final ScheduledExecutorService scheduler = Executors.newSingleThreadScheduledExecutor();

    public void startWhispering() {
        scheduleNextWhisper();
    }

    private void scheduleNextWhisper() {
        long delaySeconds = 60 + random.nextInt(61); // 60 to 120 seconds
        scheduler.schedule(() -> {
            sendWhisper(pickRandomWhisper());
            scheduleNextWhisper();
        }, delaySeconds, TimeUnit.SECONDS);
    }

    private String pickRandomWhisper() {
        return WHISPERS.get(random.nextInt(WHISPERS.size()));
    }

    private void sendWhisper(String text) {
        // Replace this with actual whisper/send logic:
        System.out.println("Whisper to player: " + text);
    }

    public static void main(String[] args) {
        BondageProjectsWhisperer whisperer = new BondageProjectsWhisperer();
        whisperer.startWhispering();

        // Keep the program running indefinitely
        try {
            Thread.sleep(Long.MAX_VALUE);
        } catch (InterruptedException e) {
            Thread.currentThread().interrupt();
        }
    }
}
